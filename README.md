## Flask Application Design for Sports Wearable Products Landing Website

### HTML Files

- **index.html**: The homepage of the website, displaying general information about the brand, its products, and the environmental impact tracking features.
- **products.html**: A page dedicated to showcasing the individual sports wearable products, their specifications, and pricing.
- **cart.html**: A page displaying the user's shopping cart, allowing them to review their selected products, adjust quantities, and proceed to checkout.

### Routes

- **Home Route**: Maps to the `/` endpoint and renders the **index.html** page.
- **Products Route**: Maps to the `/products` endpoint and renders the **products.html** page.
- **Add to Cart Route**: Maps to the `/add-to-cart` endpoint and handles adding a product to the user's shopping cart.
- **Cart Route**: Maps to the `/cart` endpoint and renders the **cart.html** page, allowing users to manage their cart.
- **Checkout Route**: Maps to the `/checkout` endpoint and handles the checkout process, collecting user information and payment details.

### Implementation Details

#### HTML Files

**index.html**
- Header with the brand logo and navigation menu.
- Hero section showcasing the main message and call-to-action button.
- Sections describing the products, environmental impact tracking, and brand values.
- Footer with contact information and social media links.

**products.html**
- List of products with images, descriptions, and prices.
- "Add to Cart" button for each product.
- Filtering and sorting options to enhance user experience.

**cart.html**
- Table displaying the selected products, quantities, and subtotal.
- Option to remove items from the cart.
- "Checkout" button to proceed to the checkout page.

#### Routes

**Home Route**
- Imports the **index.html** file and renders it.

```python
@app.route('/')
def home():
    return render_template('index.html')
```

**Products Route**
- Imports the **products.html** file and renders it.

```python
@app.route('/products')
def products():
    return render_template('products.html')
```

**Add to Cart Route**
- Adds the product to the user's shopping cart.
- Redirects to the **products.html** page.

```python
@app.route('/add-to-cart', methods=['POST'])
def add_to_cart():
    # Code to add the product to the cart.
    
    return redirect(url_for('products'))
```

**Cart Route**
- Imports the **cart.html** file and renders it.

```python
@app.route('/cart')
def cart():
    return render_template('cart.html')
```

**Checkout Route**
- Handles the checkout process.
- Redirects to a confirmation page or payment processor.

```python
@app.route('/checkout')
def checkout():
    # Code to handle checkout.
    
    return redirect(url_for('confirmation'))
```

This design provides a complete flow for a landing website for the sports wearable products, allowing users to browse products, add them to their cart, and complete their purchases.