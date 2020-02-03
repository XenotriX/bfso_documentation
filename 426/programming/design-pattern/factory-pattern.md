# Factory-Pattern

#### Vorteile:

* Je nach Konfiguration kann eine Andere Business Logik verwendet werden

{% code title="Program.cs" %}
```csharp
using System;

namespace FactoryPattern
{
    class Program
    {
        static void Main(string[] args)
        {
            //var myObject = new ConcreteBusinessObject();
            var myObject = ObjectFactory.Create();
            myObject.SomethingInteresting();
        }
    }
}
```
{% endcode %}

{% code title="ObjectFactory.cs" %}
```csharp
using System;
using System.Collections.Generic;
using System.Text;

namespace FactoryPattern
{
    public static class ObjectFactory
    {
        public static IBusinessThingy Create()
        { 
            if (true)
            {
                return new ConcreteBusinessObject("something");
            }
            else {
                return new SecoundConcreteBusinessObject("something");
            }
        }
    }
}
```
{% endcode %}

{% code title="IBusinessThingy.cs" %}
```csharp
using System;
using System.Collections.Generic;
using System.Text;

namespace FactoryPattern
{
    public interface IBusinessThingy
    {
        void SomethingInteresting(); 
    }
}
```
{% endcode %}

{% code title="ConcreteBusinessObject.cs" %}
```csharp
using System;
using System.Collections.Generic;
using System.Text;

namespace FactoryPattern
{
    class ConcreteBusinessObject : IBusinessThingy
    {
        public ConcreteBusinessObject(string name) 
        { 
            
        }

        public void SomethingInteresting()
        {
            
        }
    }
}

```
{% endcode %}

{% code title="SecoundConcreteBusinessObject.cs" %}
```csharp
using System;
using System.Collections.Generic;
using System.Text;

namespace FactoryPattern
{
    class SecoundConcreteBusinessObject : IBusinessThingy
    {
        public SecoundConcreteBusinessObject(string name) { 
        
        }

        public void SomethingInteresting()
        {
   
        }
    }
}

```
{% endcode %}

