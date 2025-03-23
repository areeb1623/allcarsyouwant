<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AllCarsYouWant</title>
    <style>
        /* Keep your previous CSS here */
    </style>
</head>
<body>
    <!-- Your existing HTML structure -->

    <script>
        // Curated car data with working image links
        const cars = [
            {
                make: "Tesla",
                model: "Cybertruck",
                year: 2024,
                price: 61990,
                power: "845 hp",
                image: "https://upload.wikimedia.org/wikipedia/commons/5/5c/Tesla_Cybertruck_outside_Unplugged_Performance.jpg",
                specs: {
                    acceleration: "2.9s 0-60mph",
                    range: "340 miles",
                    drivetrain: "AWD"
                }
            },
            {
                make: "Porsche",
                model: "911 GT3",
                year: 2023,
                price: 169900,
                power: "502 hp",
                image: "https://upload.wikimedia.org/wikipedia/commons/3/3c/2022_Porsche_911_GT3_%28front%29.jpg",
                specs: {
                    acceleration: "3.2s 0-60mph",
                    topSpeed: "197 mph",
                    engine: "4.0L Flat-6"
                }
            }
        ];

        // Generate car cards
        function generateCarCards() {
            const grid = document.getElementById('carGrid');
            grid.innerHTML = '';
            
            cars.forEach(car => {
                const card = document.createElement('div');
                card.className = 'car-card';
                card.innerHTML = `
                    <div class="car-image" 
                         style="background-image: url('${car.image}')">
                    </div>
                    <div class="car-info">
                        <h3>${car.make} ${car.model}</h3>
                        <div class="car-specs">
                            <div class="spec-item">⚡️ ${car.power}</div>
                            <div class="spec-item">🏁 ${car.specs.acceleration}</div>
                            <div class="spec-item">💰 $${car.price.toLocaleString()}</div>
                        </div>
                        <button class="cyber-button">Details</button>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        // Initialize on load
        window.onload = generateCarCards;
    </script>
</body>
</html>
