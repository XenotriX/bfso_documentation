# Scripts

#### Console Output \(Debug\)

```csharp
Debug.Log("Hello World");
```

#### Add force to a Rigidbody

```csharp
    public Rigidbody rb;

    // Update is called once per frame
    void FixedUpdate()
    {
        rb.AddForce(0, 0, 2000 * Time.deltaTime);
    }
```

{% hint style="info" %}
Use FixedUpdate when dealing with physics
{% endhint %}

#### Using Keys

```csharp
    if (Input.GetKey("d")) {
        rb.AddForce(500 * Time.deltaTime, 0, 0);
    }
```

#### FollowPlayer Camera

```csharp
using UnityEngine;

public class FollowPlayer : MonoBehaviour
{
    public Transform player;
    public Vector3 offset;

    // Update is called once per frame
    void Update()
    {
        transform.position = player.position + offset;
    }
}
```

#### PlayerMovement

```csharp
public class PlayerMovement : MonoBehaviour
{
    public Rigidbody rb;

    public float forwardForce = 2000f;
    public float sidewaysForce = 100f;

    // Update is called once per frame
    void FixedUpdate()
    {
        // Add a forward force
        rb.AddForce(0, 0, forwardForce * Time.deltaTime);

        if (Input.GetKey("d")) {
            rb.AddForce(sidewaysForce * Time.deltaTime, 0, 0, ForceMode.VelocityChange);
        }
        if (Input.GetKey("a"))
        {
            rb.AddForce(-sidewaysForce * Time.deltaTime, 0, 0, ForceMode.VelocityChange);
        }
    }
}
```

