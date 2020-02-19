# Singelton-Pattern



```csharp
using System;

namespace Singelton
{
    class Program
    {
        static void Main(string[] args)
        {
            MySingelton mySingelton = MySingelton.Instance;
            mySingelton.DoSomething();
        }
    }

    public class MySingelton
    {
        private static MySingelton instance;
        private MySingelton() { }

        public static MySingelton Instance
        {
            get {
                if (instance == null) {
                    instance = new MySingelton();
                }
                return instance; 
            }
        }

        public void DoSomething() {
            Console.WriteLine("Singelton Class code has been called");
        }
    }
}

```

#### Thread-Save-Singelton

{% embed url="https://www.youtube.com/watch?v=XZl3FgkYazI" %}

## Links

{% embed url="https://phpenthusiast.com/blog/the-singleton-design-pattern-in-php" %}



