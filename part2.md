# Part 2: Creating the landing page


For the second part, we will create a landing page that:

1. Displays a message with a typing effect.
2. Takes the text dynamically as an input.
3. Automatically transitions to the next page (page2.html) after 20 seconds.


### Setting up the HTML

We will add the following to our index.html. 

```html

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> Title of page</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <!-- Main Container -->
    <div class="main-container">
        <p>Dear crush, I have a message for you</p>
    </div>

    <script src="script.js"></script>
</body>
</html>


```


### Creating a typing effect using javascript.

We'll define a reusable function that takes:

1. The target element ID where the text will appear.
2. The text to be typed out.

Update script.js with the following:

```javascript


function createTypingEffect(elementId, text, speed = 100) {

    /**
    * Helper function to create a typing effect.
    *  elementId - The ID of the HTML element to display text.
    *  text - The text to type out.
    *  speed - Typing speed in milliseconds (default is 100ms).
 */
    const element = document.getElementById(elementId);
    let index = 0;

    function typeNextLetter() {
        if (index < text.length) {
            element.textContent += text.charAt(index);
            index++;
            setTimeout(typeNextLetter, speed);
        }
    }

    typeNextLetter();
}


```


### Creating the page transition

We will update our javascript to redirect the page after sometime. 

```javascript
    // Redirect to page2.html after 20 seconds

    setTimeout(() => {
    window.location.href = "page2.html";
}, 20000);
```

Now, lets use the our helper function to display our landing message.

```javascript
    createTypingEffect("landing-message", "Will you be my valentine?", 100);
```

The next step is to modify our index.html page by setting the id for our container. 

```html
    <div class="main-container">
        <p id="landing-message"></p>
    </div>
```
