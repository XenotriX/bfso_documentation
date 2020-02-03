# Example xkcd API

Code based on

{% embed url="https://www.youtube.com/watch?v=aWePkE2ReGw" %}



{% code title="ApiHelper.cs" %}
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Net.Http;
using System.Net.Http.Headers;

namespace DemoLibrary
{
    public class ApiHelper
    {
        public static HttpClient ApiClient { get; set; }

        public static void InitializeClient() {
            ApiClient = new HttpClient();

            // Only a json response is accepted
            ApiClient.DefaultRequestHeaders.Accept.Clear();
            ApiClient.DefaultRequestHeaders.Accept.Add(new MediaTypeWithQualityHeaderValue("application/json"));
        }
    }
}
```
{% endcode %}

{% code title="ComicModel.cs" %}
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace DemoLibrary
{
    public class ComicModel
    {
        public int Num { get; set; }
        public string Img { get; set; }
    }
}

```
{% endcode %}

{% code title="ComicProcessor.cs" %}
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;

namespace DemoLibrary
{
    /**
     * The ComicProcessor is responsible for calling the api
     * and mapping the data into the ComicModel. 
     */
    public class ComicProcessor
    {
        public static async Task<ComicModel> LoadComic(int comicNumber = 0)
        {
            string url = "";

            // The API allows to get a specific comic or the latest one
            if (comicNumber > 0)
            {
                url = $"http://xkcd.com/{comicNumber}/info.0.json";
            }
            else
            {
                url = $"http://xkcd.com/info.0.json";
            }

            // The keyword 'using' automatically cleans up after the closing {
            using (HttpResponseMessage response = await ApiHelper.ApiClient.GetAsync(url))
            {
                // IsSuccessStatusCode means that when the HTTP Status Code is between 200 and 299
                if (response.IsSuccessStatusCode)
                {
                    // We are waiting here until we get an answer
                    ComicModel comic = await response.Content.ReadAsAsync<ComicModel>();
                    return comic;
                }
                else {
                    throw new Exception(response.ReasonPhrase);
                }
            }
        }
    }
}

```
{% endcode %}

```csharp
using DemoLibrary;
using System;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Media.Imaging;

namespace WPFApp
{
    public partial class MainWindow : Window
    {
        private int maxNumber = 0;
        private int currentNumber = 0;

        public MainWindow()
        {
            // Initialize the wpf form
            InitializeComponent();

            // Initialize the httpClient
            ApiHelper.InitializeClient();

            // We start at the last comic - so the next button should be disabled
            nextImageButton.IsEnabled = false;
        }

        /**
         * When the form is ready we load the latest image
         * Usually async needs to retrun a Task, but here its okay to retrun void
         */
        private async void Window_Loaded(object sender, RoutedEventArgs e)
        {
            await LoadImage();
        }

        /** 
         * Every method that contains a 'await' needs to be 'async'
         */
        private async Task LoadImage(int imageNumber = 0) {
            var comic = await ComicProcessor.LoadComic(imageNumber);
            if (imageNumber == 0)
            {
                maxNumber = comic.Num;
            }
            currentNumber = comic.Num;
            comicImage.Source = GetBitmapImage(comic.Img);
        }

        /**
         * This function returns an BitmapImage based on an url
         */
        private BitmapImage GetBitmapImage(string imageUrl) {
            var uriSource = new Uri(imageUrl, UriKind.Absolute);
            return new BitmapImage(uriSource);
        }

        private async void previousImageButton_Click(object sender, RoutedEventArgs e)
        {
            if (currentNumber > 1) {
                currentNumber -= 1;
                nextImageButton.IsEnabled = true;
                await LoadImage(currentNumber);

                if (currentNumber == 1)
                {
                    previousImageButton.IsEnabled = false;
                }
            }
        }

        private async void nextImageButton_Click(object sender, RoutedEventArgs e)
        {
            if (currentNumber < maxNumber)
            {
                currentNumber += 1;
                previousImageButton.IsEnabled = true;
                await LoadImage(currentNumber);

                if (currentNumber == maxNumber)
                {
                    nextImageButton.IsEnabled = false;
                }
            }
        }
    }
}

```

