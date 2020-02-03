# Single-Responsibility-Prinzip

{% hint style="info" %}
Es sollte nie mehr als einen Grund dafür geben, eine Klasse zu ändern.
{% endhint %}

### Step 1

{% code title="app/Http/Controllers/ProductController.php" %}
```php
    public function store(Request $request)
    {
        $validatedData = $request->validate([
            'name' => 'required',
            'price' => 'numeric',
        ]);
        
        // [..]
    
        $product = new Product();
        $product->name = $request->name;
        $product->price = $request->price;
        $product->save();

        return redirect(route('products.index'));
    }
```
{% endcode %}

### Step 2

{% code title="app/Http/Controllers/ProductController.php" %}
```php
    public function store(ProductRequest $request)
    {
        $product = new Product();
        $product->name = $request->name;
        $product->price = $request->price;
        $product->save();

        return redirect(route('products.index'));
    }
```
{% endcode %}

### Step 3

{% code title="app/Http/Controllers/ProductController.php" %}
```php
    public function store(ProductRequest $request)
    {
        ProductRepository::save($request);
        return redirect(route('products.index'));
    }
```
{% endcode %}

