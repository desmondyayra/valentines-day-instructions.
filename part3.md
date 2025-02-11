# Part 2: Adding User Interaction
---

## JavaScript

Now it is time to set the foundation for the interactive bits for your website. In this section, we will: Set the messages someone gets when they click no, and what will happen when your special someone clicks either yes or no. Open `script.js` and let us get started. 

### No Messages :(

In the unfortunate case that someone clicks the no button, we will rotate messages that will hopefully convince them to click the yes button. This loop will happen until someone clicks yes.
 
Using the `const` keyword, we will declare a constant variable that holds our messages for when someone hits no. Let's name this variable `noButtonPhrases`.

Now set that variable to an array that will hold your phrases, each phrase should be an enclosed string separated by a comma (Suggestion: indenting after every phrase may help organize your code). 

Once you curate your many phrases, we can close the array. It should be formatted like this:

```javascript
const noButtonPhrases = [
    "Please", 
    "Please", 
    "Please", 
    "Pleaseeeeee", 
    "Please", 
    "Please", 
    "Please", 
    "Please",
];
```

Now that we have your beautiful array, here are some variables I’d like you to paste into your file that will help you with your next tasks. (In case you wanted to know what the variables did, comments were left for your guidance)
 
```javascript
// keeps track of the number of times the user has clicked the no button
let numberOfTimesClicked = 0; 
// this gives us access to the no button and the yes button
const yesButton = document.getElementById("yes-button"); 
const noButton = document.getElementById("no-button");
// we also need to get the DOM element for the gif
const gif = document.getElementById("gif-container");
// we need to access the DOM element for the main text
const mainText = document.getElementById("main-text");
```

### No Button Actions :/ 

As the user hits the No Button, we want 3 things to happen simultaneously.
1. The phrase on the No Button to shift
2. We want our Yes Button to get bigger
3. We want our No button to be placed randomly on the user’s window

```javascript
noButton.addEventListener("click", () => {
    // Insert Tasks Here
});
```

Copy this function (basically tells our website what to execute when the No Button is clicked) onto your file, and let's start. 

Using the `numberOfTimesClicked` variable I told you to paste, we will use this variable to keep track of the number of times the no button is clicked. This will come in handy for our first two tasks.

Where `// Insert Tasks Here is Located` add `numberOfTimesClicked++` to the things that happen, this will add one to the variable `numberOfTimesClicked` every time the No Button is clicked. After closing this line with a semicolon, you may be wondering, what happens if my recipients hit the No Button 1129 times? Do we have 1129 responses ready? Well fear not, depending on the amount of strings you wrote in `noButtonPhrases`, which may or may not be greater or equal to 1129, it determines the upper limit of our variable `numberOfTimesClicked`.

To do this we need to set an inequality using the `if` statement, which asks if the `numberOfTimesClicked` is greater than the length of `noButtonPhrases` then we reset the counter of `numberOfTimesClicked` to zero. 

This statement should look like this:
```javascript
if (numberOfTimesClicked >= noButtonPhrases.length) {
    numberOfTimesClicked = 0;
};
```

Now let us input a line that changes the phrase of the No Button when the no button is clicked. Using our handy dandy `numberOfTimesClicked` variable we can use that to retrieve that numbered phrase within our array! Then we can set that as our new No Button text content. 

This should look like this: 
```javascript
noButton.textContent = noButtonPhrases[numberOfTimesClicked];
```

Now if your recipient hits the No Button, we need something that emphasizes the Yes Button a little bit more. With the help of `numberOfTimesClicked`, we can multiply the size of our Yes Button by the amount of times No is clicked. 

By accessing the yes button from the CSS file using `yesButton.style.fontSize`, we can set it to a new value depending on the value of `numberOfTimesClicked`

Given that the font size of the button is already 20px, we can alter the font size in increments of 10 depending on `numberOfTimesClicked`. Place that expression within `${}` 

The final product of this should look like this:
```javascript
yesButton.style.fontSize = `${numberOfTimesClicked * 10 + 20}px`;
```

Now let us move the No button around the user’s screen so that hopefully they can just click the Yes button in the place of time and effort.

Paste these variables into your function:
```javascript
const randomX = Math.random() * (window.innerWidth - noButton.clientWidth);
const randomY = Math.random() * (window.innerHeight - noButton.clientHeight);
```

These variables will produce a random X or Y coordinate within the user's screen every time the No Button is clicked ensuring that the No Button won't overflow on the screen. 

Now to set the position of this we have to first set the position of the no button to be absolute, then we tell where the button to go through the previous variables to set as the new left and top properties.  

```javascript
noButton.style.position = 'absolute'; // set position to absolute
noButton.style.left = `${randomX}px`;
noButton.style.top = `${randomY}px`;
```

Congrats adding this all together will grant you something like this!

```javascript
noButton.addEventListener("click", () => {
    numberOfTimesClicked++;
    if (numberOfTimesClicked >= noButtonPhrases.length) {
        numberOfTimesClicked = 0;
    }; 
    noButton.textContent

 = noButtonPhrases[numberOfTimesClicked];
    yesButton.style.fontSize = `${numberOfTimesClicked * 10 + 20}px`;

    const randomX = Math.random() * (window.innerWidth - noButton.clientWidth);
    const randomY = Math.random() * (window.innerHeight - noButton.clientHeight);
    noButton.style.position = 'absolute'; // set position to absolute
    noButton.style.left = `${randomX}px`;
    noButton.style.top = `${randomY}px`;
});
```

Too much talking about getting rejected, let's see how we celebrate getting a yes!

### Yes Button Actions :) 

When the user hits the yes button, we want 3 things to happen.
1. Change the GIF
2. Change the main text
3. Remove the buttons from the screen. 

Just like the No Button, here is the function that takes in the user’s clicking of the button as the input:

```javascript
yesButton.addEventListener("click", () => {
    // Insert Tasks Here!
});
```

Unlike the previous actions, when the user hits yes we only have to remove and set variables to new values. 

To remove the buttons, we set the style property of both buttons to “none”. 

To change the GIF and the main text, we just set the variables responsible for this to the new message and GIF link we want to display (`gif.src` for the new GIF Link, `mainText.textContent` for the new message). Make sure these are all in strings!

Your finished product should look like this:
```javascript
yesButton.addEventListener("click", () => {
    yesButton.style.display = "none";
    noButton.style.display = "none";
    gif.src = "https://media.tenor.com/TEC6z0acIbUAAAAj/cute-bears-love.gif";
    mainText.textContent = "yay! i knew you would say yes! <3";
});
```

Congrats! The foundation for the website is now set, let's see how we can deploy this site and send it to your special someone ;) 

---