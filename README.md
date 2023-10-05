<!DOCTYPE html>
<html>
<head>
    <title>Furniture Selection</title>
    <style>
        /* Add CSS styles here */
    </style>
</head>
<body>
    <h1>Furniture Selection</h1>
    <label for="wallLength">Enter Wall Length (in inches):</label>
    <input type="number" id="wallLength" placeholder="Enter wall length">
    <button onclick="generateFurnitureOptions()">Generate Options</button>
    <div id="furnitureOptions">
        <!-- Furniture options will be displayed here dynamically -->
    </div>

    <script>
        function generateFurnitureOptions() {
            const wallLength = parseInt(document.getElementById("wallLength").value);
            const furnitureOptions = ["Sofa", "Bookshelf", "Table", "Bed"]; // Sample furniture options

            const validOptions = furnitureOptions.filter(option => {
                return wallLength >= getFurnitureLength(option);
            });

            const optionsList = document.getElementById("furnitureOptions");
            optionsList.innerHTML = "";

            if (validOptions.length === 0) {
                optionsList.innerHTML = "No furniture options available for this wall length.";
            } else {
                validOptions.forEach(option => {
                    const listItem = document.createElement("p");
                    listItem.textContent = option;
                    optionsList.appendChild(listItem);
                });
            }
        }

        function getFurnitureLength(option) {
            // Replace with real data or calculations based on the furniture type
            const furnitureLengths = {
                "Sofa": 70,
                "Bookshelf": 30,
                "Table": 40,
                "Bed": 80
            };
            return furnitureLengths[option] || 0;
        }
    </script>
</body>
</html>
