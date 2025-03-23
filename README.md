[<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CarInfo Hub - All About Cars</title>
    <style>
        /* Basic CSS Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        /* Main Styles */
        body {
            background-color: #f5f5f5;
            color: #333;
            line-height: 1.6;
        }
        
        header {
            background: linear-gradient(135deg, #2c3e50, #3498db);
            color: white;
            padding: 1rem 0;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .logo {
            font-size: 2rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
        }
        
        .search-container {
            max-width: 800px;
            margin: 1rem auto;
            padding: 0 1rem;
        }
        
        .search-form {
            display: flex;
            gap: 0.5rem;
        }
        
        .search-input {
            flex: 1;
            padding: 0.8rem;
            border: 2px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }
        
        .search-button {
            background-color: #e74c3c;
            color: white;
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 4px;
            cursor: pointer;
            font-weight: bold;
            transition: background-color 0.3s;
        }
        
        .search-button:hover {
            background-color: #c0392b;
        }
        
        main {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1rem;
        }
        
        .featured-section {
            margin-bottom: 3rem;
        }
        
        .section-title {
            position: relative;
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            padding-bottom: 0.5rem;
            color: #2c3e50;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 60px;
            height: 3px;
            background-color: #e74c3c;
        }
        
        .car-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1.5rem;
        }
        
        .car-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }
        
        .car-card:hover {
            transform: translateY(-5px);
        }
        
        .car-image-container {
            height: 180px;
            overflow: hidden;
        }
        
        .car-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .car-card:hover .car-image {
            transform: scale(1.05);
        }
        
        .car-details {
            padding: 1rem;
        }
        
        .car-name {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: #2c3e50;
        }
        
        .car-info {
            color: #7f8c8d;
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
        }
        
        .view-button {
            display: inline-block;
            background-color: #3498db;
            color: white;
            text-decoration: none;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            font-size: 0.9rem;
            transition: background-color 0.3s;
        }
        
        .view-button:hover {
            background-color: #2980b9;
        }
        
        .categories-section {
            margin-bottom: 3rem;
        }
        
        .category-list {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
        }
        
        .category-item {
            background-color: white;
            border-radius: 8px;
            padding: 1.5rem;
            text-align: center;
            flex: 1;
            min-width: 160px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
            transition: transform 0.3s;
            cursor: pointer;
        }
        
        .category-item:hover {
            transform: translateY(-5px);
            background-color: #3498db;
            color: white;
        }
        
        .category-icon {
            font-size: 2rem;
            margin-bottom: 0.5rem;
        }
        
        .recent-section {
            margin-bottom: 3rem;
        }
        
        footer {
            background-color: #2c3e50;
            color: white;
            padding: 2rem 0;
            text-align: center;
        }
        
        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
            text-align: left;
            padding: 0 1rem;
        }
        
        .footer-column h3 {
            margin-bottom: 1rem;
            position: relative;
            padding-bottom: 0.5rem;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 40px;
            height: 2px;
            background-color: #e74c3c;
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 0.5rem;
        }
        
        .footer-column ul li a {
            color: #bdc3c7;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-column ul li a:hover {
            color: white;
        }
        
        .copyright {
            margin-top: 2rem;
            padding-top: 1rem;
            border-top: 1px solid rgba(255,255,255,0.1);
            font-size: 0.9rem;
            color: #bdc3c7;
        }
        
        @media (max-width: 768px) {
            .car-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
            
            .footer-content {
                grid-template-columns: 1fr;
                gap: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="logo">CarInfo Hub</div>
        <p>Your complete resource for everything automotive</p>
    </header>
    
    <div class="search-container">
        <form class="search-form" id="search-form">
            <input type="text" class="search-input" placeholder="Search by make, model, or year..." id="search-input">
            <button type="submit" class="search-button">Search</button>
        </form>
    </div>
    
    <main>
        <section class="featured-section">
            <h2 class="section-title">Popular Cars</h2>
            <div class="car-grid">
                <!-- Car Card 1 -->
                <div class="car-card">
                    <div class="car-image-container">
                        <img src="/api/placeholder/250/180" alt="Tesla Model S" class="car-image">
                    </div>
                    <div class="car-details">
                        <h3 class="car-name">Tesla Model S</h3>
                        <p class="car-info">Electric Sedan • 2023</p>
                        <p class="car-info">Range: 405 miles</p>
                        <a href="#" class="view-button">View Details</a>
                    </div>
                </div>
                
                <!-- Car Card 2 -->
                <div class="car-card">
                    <div class="car-image-container">
                        <img src="/api/placeholder/250/180" alt="Toyota Camry" class="car-image">
                    </div>
                    <div class="car-details">
                        <h3 class="car-name">Toyota Camry</h3>
                        <p class="car-info">Midsize Sedan • 2023</p>
                        <p class="car-info">MPG: 28 city / 39 hwy</p>
                        <a href="#" class="view-button">View Details</a>
                    </div>
                </div>
                
                <!-- Car Card 3 -->
                <div class="car-card">
                    <div class="car-image-container">
                        <img src="/api/placeholder/250/180" alt="Ford F-150" class="car-image">
                    </div>
                    <div class="car-details">
                        <h3 class="car-name">Ford F-150</h3>
                        <p class="car-info">Pickup Truck • 2023</p>
                        <p class="car-info">Towing: 14,000 lbs</p>
                        <a href="#" class="view-button">View Details</a>
                    </div>
                </div>
                
                <!-- Car Card 4 -->
                <div class="car-card">
                    <div class="car-image-container">
                        <img src="/api/placeholder/250/180" alt="Honda CR-V" class="car-image">
                    </div>
                    <div class="car-details">
                        <h3 class="car-name">Honda CR-V</h3>
                        <p class="car-info">Compact SUV • 2023</p>
                        <p class="car-info">MPG: 28 city / 34 hwy</p>
                        <a href="#" class="view-button">View Details</a>
                    </div>
                </div>
            </div>
        </section>
        
        <section class="categories-section">
            <h2 class="section-title">Browse by Category</h2>
            <div class="category-list">
                <div class="category-item">
                    <div class="category-icon">🚗</div>
                    <h3>Sedans</h3>
                </div>
                <div class="category-item">
                    <div class="category-icon">🚙</div>
                    <h3>SUVs</h3>
                </div>
                <div class="category-item">
                    <div class="category-icon">🏎️</div>
                    <h3>Sports Cars</h3>
                </div>
                <div class="category-item">
                    <div class="category-icon">🚐</div>
                    <h3>Minivans</h3>
                </div>
                <div class="category-item">
                    <div class="category-icon">🛻</div>
                    <h3>Trucks</h3>
                </div>
                <div class="category-item">
                    <div class="category-icon">⚡</div>
                    <h3>Electric</h3>
                </div>
            </div>
        </section>
        
        <section class="recent-section">
            <h2 class="section-title">Recent Additions</h2>
            <div class="car-grid">
                <!-- Car Card 1 -->
                <div class="car-card">
                    <div class="car-image-container">
                        <img src="/api/placeholder/250/180" alt="Nissan Altima" class="car-image">
                    </div>
                    <div class="car-details">
                        <h3 class="car-name">Nissan Altima</h3>
                        <p class="car-info">Midsize Sedan • 2023</p>
                        <p class="car-info">MPG: 28 city / 39 hwy</p>
                        <a href="#" class="view-button">View Details</a>
                    </div>
                </div>
                
                <!-- Car Card 2 -->
                <div class="car-card">
                    <div class="car-image-container">
                        <img src="/api/placeholder/250/180" alt="Jeep Wrangler" class="car-image">
                    </div>
                    <div class="car-details">
                        <h3 class="car-name">Jeep Wrangler</h3>
                        <p class="car-info">SUV • 2023</p>
                        <p class="car-info">MPG: 17 city / 25 hwy</p>
                        <a href="#" class="view-button">View Details</a>
                    </div>
                </div>
                
                <!-- Car Card 3 -->
                <div class="car-card">
                    <div class="car-image-container">
                        <img src="/api/placeholder/250/180" alt="Chevrolet Corvette" class="car-image">
                    </div>
                    <div class="car-details">
                        <h3 class="car-name">Chevrolet Corvette</h3>
                        <p class="car-info">Sports Car • 2023</p>
                        <p class="car-info">0-60 mph: 2.9 sec</p>
                        <a href="#" class="view-button">View Details</a>
                    </div>
                </div>
                
                <!-- Car Card 4 -->
                <div class="car-card">
                    <div class="car-image-container">
                        <img src="/api/placeholder/250/180" alt="Hyundai Tucson" class="car-image">
                    </div>
                    <div class="car-details">
                        <h3 class="car-name">Hyundai Tucson</h3>
                        <p class="car-info">Compact SUV • 2023</p>
                        <p class="car-info">MPG: 26 city / 33 hwy</p>
                        <a href="#" class="view-button">View Details</a>
                    </div>
                </div>
            </div>
        </section>
    </main>
    
    <footer>
        <div class="footer-content">
            <div class="footer-column">
                <h3>About CarInfo Hub</h3>
                <p>Your trusted source for comprehensive car information, specifications, reviews, and comparisons.</p>
            </div>
            
            <div class="footer-column">
                <h3>Quick Links</h3>
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Popular Cars</a></li>
                    <li><a href="#">New Releases</a></li>
                    <li><a href="#">Compare Cars</a></li>
                    <li><a href="#">Car Reviews</a></li>
                </ul>
            </div>
            
            <div class="footer-column">
                <h3>Car Categories</h3>
                <ul>
                    <li><a href="#">Sedans</a></li>
                    <li><a href="#">SUVs & Crossovers</a></li>
                    <li><a href="#">Sports Cars</a></li>
                    <li><a href="#">Trucks & Pickups</a></li>
                    <li><a href="#">Electric Vehicles</a></li>
                </ul>
            </div>
            
            <div class="footer-column">
                <h3>Contact Us</h3>
                <ul>
                    <li><a href="#">Email Support</a></li>
                    <li><a href="#">Feedback</a></li>
                    <li><a href="#">Report an Issue</a></li>
                    <li><a href="#">Request a Feature</a></li>
                </ul>
            </div>
        </div>
        
        <div class="copyright">
            &copy; 2025 CarInfo Hub. All rights reserved.
        </div>
    </footer>
    
    <script>
        // Simple search functionality
        document.getElementById('search-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const searchTerm = document.getElementById('search-input').value.toLowerCase();
            alert('Searching for: ' + searchTerm + '\n\nIn a real implementation, this would query a database of car information.');
        });
        
        // In a real implementation, you would:
        // 1. Fetch car data from a database or API
        // 2. Create car cards dynamically based on the data
        // 3. Implement proper search functionality
        // 4. Add pagination for large datasets
        // 5. Create detailed car pages
    </script>
</body>
</html>
](https://claude.site/artifacts/b4acc0aa-93b0-4b8d-be88-9710e3b27f83)
