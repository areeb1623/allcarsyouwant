<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AllCarsYouWant</title>
    <link href="https://fonts.googleapis.com/css2?family=Electrolize&display=swap" rel="stylesheet">
    <style>
        /* Your previous futuristic CSS here */
    </style>
</head>
<body>
    <!-- Your existing header/search/filter structure -->

    <script>
        // Fetch car data from NHTSA API
        async function fetchCars(make = 'Tesla') {
            const response = await fetch(`https://vpic.nhtsa.dot.gov/api/vehicles/GetModelsForMake/${make}?format=json`);
            const data = await response.json();
            return data.Results;
        }

        // Fetch images from Wikimedia
        async function fetchCarImage(make, model) {
            const response = await fetch(`https://en.wikipedia.org/w/api.php?action=query&titles=${make} ${model}&prop=pageimages&format=json&pithumbsize=300`);
            const data = await response.json();
            const page = Object.values(data.query.pages)[0];
            return page.thumbnail ? page.thumbnail.source : 'placeholder.jpg';
        }

        // Generate cards with real data
        async function generateCarCards() {
            const cars = await fetchCars();
            const grid = document.getElementById('carGrid');
            
            for(const car of cars) {
                const imageUrl = await fetchCarImage(car.MakeName, car.Model_Name);
                const card = document.createElement('div');
                card.className = 'car-card';
                card.innerHTML = `
                    <div class="car-image" style="background-image: url('${imageUrl}')"></div>
                    <div class="car-info">
                        <h3>${car.MakeName} ${car.Model_Name}</h3>
                        <div class="car-specs">
                            <div>Make Year: ${car.MakeYear}</div>
                            <div>Vehicle Type: ${car.VehicleTypeName}</div>
                        </div>
                    </div>
                `;
                grid.appendChild(card);
            }
        }

        generateCarCards();
    </script>
</body>
</html>
