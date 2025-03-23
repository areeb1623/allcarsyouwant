<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AllCarsYouWant | Ultimate Car Database</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&family=Electrolize&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #00ffea;
            --background-color: #0a0a0a;
            --card-bg: rgba(255, 255, 255, 0.05);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: var(--background-color);
            color: #ffffff;
            font-family: 'Roboto', sans-serif;
            min-height: 100vh;
        }

        /* Header Styles */
        .cyber-header {
            background: linear-gradient(180deg, #000 0%, rgba(0, 0, 0, 0.8) 100%);
            padding: 1rem 5%;
            border-bottom: 2px solid var(--primary-color);
            box-shadow: 0 0 30px rgba(0, 255, 234, 0.1);
        }

        .logo {
            font-family: 'Electrolize', sans-serif;
            font-size: 2rem;
            color: var(--primary-color);
            text-transform: uppercase;
            letter-spacing: 4px;
        }

        /* Search Section */
        .search-section {
            padding: 3rem 5%;
            background: radial-gradient(circle at center, #001a1a 0%, #000 100%);
        }

        .cyber-search {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        #searchInput {
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid var(--primary-color);
            padding: 1rem;
            color: white;
            font-size: 1.2rem;
            border-radius: 5px;
            transition: all 0.3s;
        }

        /* Filter Section */
        .filters {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1rem;
            padding: 2rem 5%;
            background: rgba(0, 0, 0, 0.7);
        }

        .filter-dropdown {
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid var(--primary-color);
            color: white;
            padding: 0.8rem;
            border-radius: 5px;
            cursor: pointer;
        }

        /* Car Grid */
        .car-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            padding: 3rem 5%;
        }

        .car-card {
            background: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            border: 1px solid var(--primary-color);
            transition: transform 0.3s, box-shadow 0.3s;
            backdrop-filter: blur(10px);
        }

        .car-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 30px rgba(0, 255, 234, 0.2);
        }

        .car-image {
            height: 200px;
            background-size: cover;
            background-position: center;
            position: relative;
        }

        .car-info {
            padding: 1.5rem;
        }

        .car-specs {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1rem;
            margin-top: 1rem;
        }

        .spec-item {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        /* Cyber Elements */
        .cyber-border {
            position: relative;
            padding: 2px;
            background: linear-gradient(45deg, transparent 50%, var(--primary-color) 50%);
            background-size: 3px 3px;
        }

        @media (max-width: 768px) {
            .cyber-search {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header class="cyber-header">
        <div class="logo">AllCarsYouWant</div>
    </header>

    <section class="search-section">
        <div class="cyber-search">
            <input type="text" id="searchInput" placeholder="Search 1,000,000+ vehicles...">
            <button class="cyber-button">ADVANCED FILTERS</button>
        </div>
    </section>

    <section class="filters">
        <select class="filter-dropdown" id="makeFilter">
            <option value="">All Makes</option>
            <option>Tesla</option>
            <option>Porsche</option>
            <option>Ferrari</option>
        </select>

        <select class="filter-dropdown" id="yearFilter">
            <option value="">All Years</option>
            <option>2023</option>
            <option>2022</option>
            <option>2021</option>
        </select>

        <select class="filter-dropdown" id="priceFilter">
            <option value="">Price Range</option>
            <option>$0 - $50,000</option>
            <option>$50,000 - $100,000</option>
            <option>$100,000+</option>
        </select>

        <select class="filter-dropdown" id="typeFilter">
            <option value="">All Types</option>
            <option>Electric</option>
            <option>Sports</option>
            <option>SUV</option>
        </select>
    </section>

    <main class="car-grid" id="carGrid">
        <!-- Car cards will be dynamically inserted here -->
        <div class="car-card">
            <div class="car-image" style="background-image: url('https://example.com/tesla-cybertruck.jpg')"></div>
            <div class="car-info">
                <h3>Tesla Cybertruck</h3>
                <div class="car-specs">
                    <div class="spec-item">
                        <span>⚡️</span> 500 hp
                    </div>
                    <div class="spec-item">
                        <span>⏱️</span> 2.9s 0-60
                    </div>
                    <div class="spec-item">
                        <span>🔋</span> 500 mi
                    </div>
                    <div class="spec-item">
                        <span>💰</span> $69,420
                    </div>
                </div>
                <button class="cyber-button" style="margin-top: 1rem">Learn More</button>
            </div>
        </div>
    </main>

    <script>
        // Sample car data (replace with real database)
        const cars = [
            {
                make: 'Tesla',
                model: 'Cybertruck',
                price: 69420,
                year: 2023,
                type: 'Electric',
                power: '500 hp',
                acceleration: '2.9s 0-60',
                range: '500 mi',
                image: 'cybertruck.jpg'
            }
            // Add more car objects here
        ];

        // Filter functionality
        document.getElementById('searchInput').addEventListener('input', filterCars);
        document.querySelectorAll('.filter-dropdown').forEach(filter => {
            filter.addEventListener('change', filterCars);
        });

        function filterCars() {
            const searchTerm = document.getElementById('searchInput').value.toLowerCase();
            const make = document.getElementById('makeFilter').value;
            const year = document.getElementById('yearFilter').value;
            const price = document.getElementById('priceFilter').value;
            const type = document.getElementById('typeFilter').value;

            // Filter logic here (requires backend implementation)
            console.log('Filtering cars...');
        }

        // Dynamic car card generation
        function generateCarCards(cars) {
            const grid = document.getElementById('carGrid');
            grid.innerHTML = '';

            cars.forEach(car => {
                const card = document.createElement('div');
                card.className = 'car-card';
                card.innerHTML = `
                    <div class="car-image" style="background-image: url('${car.image}')"></div>
                    <div class="car-info">
                        <h3>${car.make} ${car.model}</h3>
                        <div class="car-specs">
                            <div class="spec-item">
                                <span>⚡️</span> ${car.power}
                            </div>
                            <div class="spec-item">
                                <span>⏱️</span> ${car.acceleration}
                            </div>
                            <div class="spec-item">
                                <span>🔋</span> ${car.range}
                            </div>
                            <div class="spec-item">
                                <span>💰</span> $${car.price.toLocaleString()}
                            </div>
                        </div>
                        <button class="cyber-button" style="margin-top: 1rem">Learn More</button>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        // Initial load
        generateCarCards(cars);
    </script>
</body>
</html>
