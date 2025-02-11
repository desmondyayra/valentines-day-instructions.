# Part 1: Creating the HTML Skeleton
## HTML:

Now that we pasted the previous HTML, it is time we fill in the “To-Dos”.

### Main Container

In our “Main Container Class”, we are going to implement 3 things: Our title, a cute GIF/image to complement your love advance, and your question that is sure to grab the heart of your lucky recipient. 

#### TITLE

Using the heading level 1 element (aka `<h1>`) you are going to make the title that is going to be displayed at the forefront of your website. Sorta like a greeting or whatever you want your first impression to be.

The format should look a little like this:
```html
<h1>Insert Title Here</h1>
```
Make sure you place that indented and underneath our main container.

Great, now you have a title so now let us add an image!

#### GIF

Using the `<img>` element, we are going to define 3 attributes within the angle brackets: id, src, and alt. All three of these elements will be used to allow your lovely GIF to be displayed. 

The id attribute is used to uniquely identify an element within a document, for this instance let's just name it “gif container”. By writing out `id=”gif-container”` following the opening bracket and img, `<img>` we will set the value of id to “gif-container” (Please set the id to “gif-container, the CSS file we provide uses this attribute to define the gif, so please follow the instructions. If you want to rebel :/ just make sure to change the id within the CSS file to whatever better name you had:/)

The src attribute is used to specify the URL of our GIF. First, to go find the GIF meant to capture your future soulmate, go to [Tenor](https://tenor.com/) and use the search feature to find something lovely. Now that you have found your GIF, right-click the image and copy the image address until you get a little something like this into your browser (https://c.tenor.com/1c6SJHd9aVsAAAAC/tenor.gif). Get that link and set the value of src to it. For example: `src=https://c.tenor.com/1c6SJHd9aVsAAAAC/tenor.gif`

Lovely, now we just have to give an alternate name to this GIF using the alt element. This is just for accessibility purposes, etc. Implement it following this format: `alt=”blah-blah-blah”`

Close the elements with the closing angle bracket, and now you have your GIF ready to go!

Just in case this is what the format is supposed to look like: 
```html
<img id="gif-container" src=tenor link alt="Gif of whatever you picked">
```

#### MESSAGE

It is time to shoot your shot!

Just like the title, we will implement text but this time using the `<h3>` element. Unlike the title though, we need to set the id of your smooth pick-up (so we can change it when they say yes :3) 

Within the first `<h3>` (after the opening angle bracket and “h3”), we are going to add the id of the message. For this workshop, I am going to gently ask you to please make the `id=”main-text”` (unless you wanna rebel again but then you have to go to the CSS file, your problem not mine…) and close the element with the closing angle bracket.

Now it's time for your pick-up line! Place it after the first h3 element (Like this `<h3 id=”main-text”>Message</h3>`) and now you are ready to go! 

For reference, your code should resemble something like this when you sandwich it all together: 
```html
<div class="main-container">
    <h1>Title</h1>
    <img id="gif-container" src=tenor link alt="Gif of whatever you picked">
    <h3 id="main-text">will you be my valentine?</h3>
</div>
```

### Button Container

Now we need to add the Buttons so your lovely crush can say yes! (or no, but that’s not my problem…)

Within the container, we should add two `<button>` elements with one on top of the other to represent both buttons we want on our website. Now let's differentiate each button by using id and giving the content of the button. 

Set the id of each button within the first brackets (just like `<h3>`) and make the `id=”yes-button”` and `id=”no-button”`. Close that bracket.

Follow that right up with either Yes or No depending on the button.

Close the button element with `</button>`

Your code should read: 
```html
<div class="button-container">
    <button id="yes-button">Yes</button>
    <button id="no-button">No</button>
</div>
```

Congrats you just set up the framework for your website! Now let's make it personalized!