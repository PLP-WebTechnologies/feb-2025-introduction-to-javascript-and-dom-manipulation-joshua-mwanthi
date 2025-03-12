# Introduction to JavaScript and DOM Manipulation

## Objectives

Write basic JavaScript functions.
Manipulate the DOM dynamically.
Respond to user interactions.

## Instructions

- Create a script.js file and link it to a HTML.
- Structure the document using DOCTYPE, html, head, and body.

>[!NOTE]
>  - Write JavaScript that:
>  - Changes text content dynamically.
>  - Modifies CSS styles via JavaScript.
>  - Adds or removes an element when a button is clicked.


# Tasks
- Create a well-structured HTML5 document.
- Use at least 5 different HTML elements.
- Ensure semantic correctness.

Happy Coding! 💻✨



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM Manipulation Example</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1 id="main-title">Welcome to My Website</h1>
    </header>
    <nav>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav>
    <section>
        <p id="intro-text">This is a simple website demonstrating DOM manipulation.</p>
        <button id="change-text-btn">Change Text</button>
        <button id="toggle-element-btn">Add/Remove Element</button>
    </section>
    <footer>
        <p>Footer content goes here.</p>
    </footer>
    <script src="script.js"></script>
</body>
</html>



Css

body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    text-align: center;
}

header, footer {
    background-color: #f4f4f4;
    padding: 1em;
}

nav ul {
    list-style-type: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin: 0 1em;
}

section {
    padding: 2em;
}

.hidden {
    display: none;
}

JavaScript

document.addEventListener("DOMContentLoaded", function() {
    const mainTitle = document.getElementById("main-title");
    const introText = document.getElementById("intro-text");
    const changeTextBtn = document.getElementById("change-text-btn");
    const toggleElementBtn = document.getElementById("toggle-element-btn");

    changeTextBtn.addEventListener("click", function() {
        mainTitle.textContent = "You have changed the title!";
        introText.style.color = "blue";
    });

    toggleElementBtn.addEventListener("click", function() {
        let newElement = document.getElementById("new-element");
        if (newElement) {
            newElement.remove();
        } else {
            newElement = document.createElement("p");
            newElement.id = "new-element";
            newElement.textContent = "This is a newly added element.";
            document.querySelector("section").appendChild(newElement);
        }
    });
});
