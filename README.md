<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple E-Commerce</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background: #f4f4f9;
      color: #333;
    }
    header {
      background: #2d89ef;
      color: white;
      padding: 15px;
      text-align: center;
    }
    nav {
      background: #1a5fb4;
      display: flex;
      justify-content: center;
      padding: 10px;
      gap: 20px;
    }
    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
    }
    .container {
      width: 90%;
      max-width: 1200px;
      margin: 20px auto;
    }
    .product-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 20px;
    }
    .card {
      background: white;
      padding: 15px;
      border-radius: 10px;
      text-align: center;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    }
    .card img {
      max-width: 100%;
      border-radius: 8px;
    }
    button, .btn {
      background: #2d89ef;
      color: white;
      border: none;
      padding: 10px 15px;
      border-radius: 8px;
      cursor: pointer;
      text-decoration: none;
      display: inline-block;
      margin-top: 10px;
    }
    button:hover, .btn:hover {
      background: #1a5fb4;
    }
    form {
      display: flex;
      flex-direction: column;
      gap: 15px;
    }
    input, select {
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 6px;
    }
    section {
      display: none;
    }
    section.active {
      display: block;
    }
  </style>
</head>
<body>
  <header>
    <h1>ShopEase</h1>
  </header>

  <nav>
    <a href="#" onclick="showPage('dashboard')">Dashboard</a>
    <a href="#" onclick="showPage('product')">Product</a>
    <a href="#" onclick="showPage('checkout')">Checkout</a>
  </nav>

  <div class="container">
    <!-- Dashboard -->
    <section id="dashboard" class="active">
      <h2>Available Products</h2>
      <div class="product-grid">
        <div class="card">
          <img src="https://via.placeholder.com/200" alt="Product">
          <h3>Smart Watch</h3>
          <p>$120</p>
          <button onclick="showPage('product')">View Details</button>
        </div>
        <div class="card">
          <img src="https://via.placeholder.com/200" alt="Product">
          <h3>Wireless Earbuds</h3>
          <p>$80</p>
          <button onclick="showPage('product')">View Details</button>
        </div>
        <div class="card">
          <img src="https://via.placeholder.com/200" alt="Product">
          <h3>Smartphone</h3>
          <p>$499</p>
          <button onclick="showPage('product')">View Details</button>
        </div>
      </div>
    </section>

    <!-- Product Details -->
    <section id="product">
      <div class="card">
        <img src="https://via.placeholder.com/400" alt="Product">
        <h2>Smart Watch</h2>
        <p><strong>Price:</strong> $120</p>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
           Sleek design, water-resistant, with heart-rate monitoring.</p>
        <button onclick="showPage('checkout')">Buy Now</button>
      </div>
    </section>

    <!-- Checkout -->
    <section id="checkout">
      <h2>Billing Details</h2>
      <form onsubmit="alert('Order Placed Successfully!'); return false;">
        <input type="text" placeholder="Full Name" required>
        <input type="email" placeholder="Email Address" required>
        <input type="text" placeholder="Shipping Address" required>
        <select required>
          <option value="">Select Payment Method</option>
          <option value="card">Credit/Debit Card</option>
          <option value="upi">UPI</option>
          <option value="cod">Cash on Delivery</option>
        </select>
        <button type="submit">Place Order</button>
      </form>
    </section>
  </div>

  <script>
    function showPage(pageId) {
      document.querySelectorAll("section").forEach(sec => sec.classList.remove("active"));
      document.getElementById(pageId).classList.add("active");
      window.scrollTo(0, 0);
    }
  </script>
</body>
</html>
