I'll create a modern, responsive website for a branded men's clothing store. Here's a complete HTML file with embedded CSS and JavaScript:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UrbanEdge - Premium Men's Clothing</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #1a1a1a 0%, #2d2d2d 100%);
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            color: #fff;
            text-decoration: none;
        }

        .logo span {
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #4ecdc4;
        }

        .cart-icon {
            position: relative;
            color: #fff;
            font-size: 1.5rem;
            cursor: pointer;
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: #ff6b6b;
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><rect fill="%231a1a1a" width="1200" height="600"/><path fill="%232d2d2d" d="M0 300 Q300 0 600 300 T1200 300 V600 H0 Z"/></svg>');
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            margin-top: 80px;
        }

        .hero-content h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #fff, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            color: white;
            padding: 1rem 2.5rem;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.2rem;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(255,107,107,0.4);
        }

        /* Products Section */
        .products {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 3rem;
            color: #1a1a1a;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(0,0,0,0.2);
        }

        .product-image {
            height: 250px;
            background: linear-gradient(45deg, #f0f0f0, #e0e0e0);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: #999;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-title {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            color: #1a1a1a;
        }

        .product-price {
            font-size: 1.8rem;
            font-weight: bold;
            color: #ff6b6b;
            margin-bottom: 1rem;
        }

        .product-rating {
            color: #ffd700;
            margin-bottom: 1rem;
        }

        .add-to-cart {
            width: 100%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            color: white;
            border: none;
            padding: 1rem;
            border-radius: 10px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .add-to-cart:hover {
            transform: scale(1.05);
        }

        /* Features Section */
        .features {
            background: #1a1a1a;
            color: white;
            padding: 5rem 2rem;
        }

        .features-grid {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            text-align: center;
        }

        .feature-item i {
            font-size: 3rem;
            color: #4ecdc4;
            margin-bottom: 1rem;
        }

        /* Footer */
        footer {
            background: #111;
            color: #ccc;
            text-align: center;
            padding: 3rem 2rem 1rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            color: white;
            margin-bottom: 1rem;
        }

        .footer-section a {
            color: #ccc;
            text-decoration: none;
            display: block;
            margin-bottom: 0.5rem;
        }

        .footer-section a:hover {
            color: #4ecdc4;
        }

        /* Mobile Menu */
        .mobile-menu {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .mobile-menu span {
            width: 25px;
            height: 3px;
            background: white;
            margin: 3px 0;
            transition: 0.3s;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .mobile-menu {
                display: flex;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .section-title {
                font-size: 2rem;
            }
        }

        /* Cart Modal */
        .cart-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            z-index: 2000;
        }

        .cart-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: white;
            padding: 2rem;
            border-radius: 20px;
            max-width: 500px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
        }

        .close-cart {
            float: right;
            font-size: 2rem;
            cursor: pointer;
            color: #999;
        }

        .cart-empty {
            text-align: center;
            padding: 2rem;
            color: #666;
        }

        .cart-total {
            font-size: 1.5rem;
            font-weight: bold;
            text-align: right;
            margin-top: 1rem;
        }

        .checkout-btn {
            width: 100%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            color: white;
            border: none;
            padding: 1rem;
            border-radius: 10px;
            font-size: 1.2rem;
            cursor: pointer;
            margin-top: 1rem;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <a href="#" class="logo">Urban<span>Edge</span></a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#products">Shop</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="cart-icon" onclick="toggleCart()">
                <i class="fas fa-shopping-cart"></i>
                <span class="cart-count" id="cartCount">0</span>
            </div>
            <div class="mobile-menu" onclick="toggleMobileMenu()">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>UrbanEdge</h1>
            <p>Premium Men's Clothing for the Modern Man</p>
            <a href="#products" class="cta-button">Shop Now</a>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="products">
        <h2 class="section-title">Featured Collection</h2>
        <div class="products-grid">
            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-tshirt"></i>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Classic Tee</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                    </div>
                    <div class="product-price">$49</div>
                    <button class="add-to-cart" onclick="addToCart('Classic Tee', 49)">Add to Cart</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-coat-hanger"></i>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Slim Fit Jacket</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="far fa-star"></i>
                    </div>
                    <div class="product-price">$129</div>
                    <button class="add-to-cart" onclick="addToCart('Slim Fit Jacket', 129)">Add to Cart</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-jeans"></i>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Slim Jeans</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                    </div>
                    <div class="product-price">$89</div>
                    <button class="add-to-cart" onclick="addToCart('Slim Jeans', 89)">Add to Cart</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-shoe-prints"></i>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Leather Sneakers</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="far fa-star"></i>
                    </div>
                    <div class="product-price">$159</div>
                    <button class="add-to-cart" onclick="addToCart('Leather Sneakers', 159)">Add to Cart</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-user-tie"></i>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Dress Shirt</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                    </div>
                    <div class="product-price">$79</div>
                    <button class="add-to-cart" onclick="addToCart('Dress Shirt', 79)">Add to Cart</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-hoodie"></i>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Hoodie</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                    </div>
                    <div class="product-price">$69</div>
                    <button class="add-to-cart" onclick="addToCart('Hoodie', 69)">Add to Cart</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features">
        <div class="features-grid">
            <div class="feature-item">
                <i class="fas fa-shipping-fast"></i>
                <h3>Free Shipping</h3>
                <p>Orders over $100 ship free</p>
            </div>
            <div class="feature-item">
                <i class="fas fa-undo"></i>
                <h3>Easy Returns</h3>
                <p>30-day return policy</p>
            </div>
            <div class="feature-item">
                <i class="fas fa-shield-alt"></i>
                <h3>Quality Guaranteed</h3>
                <p>Premium materials only</p>
            </div>
            <div class="feature-item">
                <i class="fas fa-credit-card"></i>
                <h3>Secure Payment</h3>
                <p>100% secure checkout</p>
            </div>
        </div>
    </section>

    <!-- Cart Modal -->
    <div id="cartModal" class="cart-modal">
        <div class="cart-content">
            <span class="close-cart" onclick="toggleCart()">&times;</span>
            <h2>Shopping Cart</h2>
            <div id="cartItems"></div>
            <div class="cart-total" id="cartTotal">$0</div>
            <button class="checkout-btn">Proceed to Checkout</button>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>UrbanEdge</h3>
                <p>Premium men's clothing for the modern lifestyle.</p>
            </div>
            <div class="footer-section">
                <h3>Quick Links</h3>
                <a href="#">New Arrivals</a>
                <a href="#">Best Sellers</a>
                <a href="#">Sale</a>
                <a href="#">Size Guide
