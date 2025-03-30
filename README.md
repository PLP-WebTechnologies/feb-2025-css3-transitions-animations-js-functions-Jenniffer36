# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Animation & Local Storage</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
        }
        .box {
            width: 100px;
            height: 100px;
            background-color: blue;
            position: relative;
            margin: 20px auto;
            transition: all 0.5s ease-in-out;
        }
        .animate {
            transform: translateX(200px);
            background-color: red;
        }
    </style>
</head>
<body>
    <h1>CSS Animation & Local Storage</h1>
    <button id="animateBtn">Animate Box</button>
    <button id="saveColor">Save Color</button>
    <button id="loadColor">Load Color</button>
    <div class="box" id="box"></div>

    <script>
        const box = document.getElementById("box");
        const animateBtn = document.getElementById("animateBtn");
        const saveColorBtn = document.getElementById("saveColor");
        const loadColorBtn = document.getElementById("loadColor");

        // Animate box on button click
        animateBtn.addEventListener("click", () => {
            box.classList.toggle("animate");
        });

        // Save the current box color in localStorage
        saveColorBtn.addEventListener("click", () => {
            const currentColor = getComputedStyle(box).backgroundColor;
            localStorage.setItem("boxColor", currentColor);
            alert("Color saved!");
        });

        // Load the saved color from localStorage
        loadColorBtn.addEventListener("click", () => {
            const savedColor = localStorage.getItem("boxColor");
            if (savedColor) {
                box.style.backgroundColor = savedColor;
            } else {
                alert("No color saved!");
            }
        });
    </script>
</body>
</html>
