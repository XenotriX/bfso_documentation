# C\# - Basics

### Namespace

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
    }
}
```

### Console

```csharp
Console.WriteLine("Hello World!");
```

### Main Methode

Die erste Methode welche ausgeführt wird

```csharp
static void Main(){}
```

### Variabeln

```csharp
// Deklarieren
int age;
// Initialisieren
age = 10;
// Ausgeben
Console.WriteLine("Hello World!"  + age);
```

### Schlaufen

```csharp
int number = 1;

while (number <= 5) {
    Console.WriteLine(number);
    number += 1;
}

for (int i = 0; i <= 5; i++) {
    Console.WriteLine(i);
}

string[] nameList = new string[3];
nameList[0] = "melvin";
nameList[1] = "jassens";
nameList[2] = "peter";

foreach (string name in nameList) {
    Console.WriteLine(name);
}
```

### Arrays

```csharp
// 2D-Array
string[,] personsTable = new string[2,2];

personsTable[0,0] = "Hans";
personsTable[0,1] = "25";

personsTable[1,0] = "Heischi";
personsTable[1,1] = "19";

Console.WriteLine("Alter Heischi: " + personsTable[1,1]);
```

```csharp
// Generic-Array
List<string> students = new List<string>();
students.Add("bob");
students.Add("joe");

Console.WriteLine("Name: " + students[1]);
Console.ReadKey();
```

### Get and set

```csharp
class Person
{
    public string Name { 
        get {
            return Name;
        }
        set {
            Name = value;
        }
    }

    public string Age { get; set; }
}
```

### 1x1

```csharp
using System;

namespace ConsoleApp1
{
    class Program
    {
        public static void PrintRowHeader(ref bool firstRow, int from, int to) {
            string line = "";
            if (firstRow)
            {
                line += "   ";

                for (int j = from; j <= to; j++)
                {
                    line = line + "  " + j;
                }
                Console.WriteLine(line);
                firstRow = false;
            }
        }

        public static void PrintRow(int i, int from, int to)
        {
            string line;
            line = "";
            for (int j = from; j <= to; j++)
            {
                if (j == from)
                {
                    line = line + "  " + i;
                }
                int product = i * j;
                line = line + "  " + product.ToString();
            }
            Console.WriteLine(line);
        }

        public static void Print1x1(int from, int to) {

            bool firstRow = true;
            for (int i = from; i <= to; i++)
            {
                PrintRowHeader(ref firstRow, from, to);
                PrintRow(i, from, to);
            }
        }

        static void Main(string[] args)
        {
            Print1x1(5,9);
        }
    }
}

```

#### using

```csharp
using (SqlConnection conn = new SqlConnection())
{

}
```

Ist dasselbe wie:

```csharp
SqlConnection conn = new SqlConnection() 
try
{

}
finally
{
    // calls the dispose method of the conn object
}
```

Man muss also nach using{} sich nicht ums Aufräumen kümmern

## Videos

{% embed url="https://www.youtube.com/watch?v=SVINDn2RJMI" %}



