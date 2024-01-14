# Random-Quote-Generator
Tutorial on how to make a random quote generator using JS

## Description
This project builds on skills in handling events and making JavaScript functions. You will make a stylish website that generates random quotes by API fetching. If you want to go above and beyond, you can implement an X button which redirects you to X and allows you to tweet the quote.

## Difficulty 
Advanced

## Prerequisites 
- JS Functions
- JS/HTML DOM
- JS Events

## Setting Up
- Download the directory zip file (click the green "Code" button, then click "Download ZIP").
- Open the zip and upload the index.html file, style.css file, and assets folder into your working directory.
- Create a JS file called script.js

## JavaScript
For this project, the HTML and CSS files have been provided for you, so you can focus on the JavaScript. Head to your script.js file and follow along.

**1. Set up variables, storing references for elements using the DOM method `document.getElementById(elementId)`.**
- Create a variable called `quoteContainer` that gets the element by ID `quote-container`.
- Create a variable called `quoteText` that gets the element by ID `quote`.
- Create a variable called `authorText` that gets the element by ID `author`.
- Create a variable called `twitterBtn` that gets the element by ID `twitter`.
- Create a variable called `newQuoteBtn` that gets the element by ID `new-quote`.
- Create a variable called `loader` that gets the element by ID `loader`.
- Create a variable called apiQuotes that stores an empty array.

**2. Visibility Functions**

To make a good website, it's very important to consider very small actions as well. We will be creating two functions that will tweak the visibility of our quote and our spinning loading image.

- Create two separate functions called `loading` and `complete`.
```
// Show Loading
function loading() {
}

// Hide Loading
function complete() {
}
//These functions control the visibility of the loading spinner ('loader') and the quote container ('quoteContainer')
```
- Inside the loading function, set the hidden attribute of the variable loader that you created equal to false and set the hidden attribute of the variable quoteContainer equal to true.
- Inside the complete function, you will do the same thing as you did in the loading function, except, set the hidden attribute of the two variables to the opposite of what you set it as in the loading function.

**3. Show New Quote**

You will now be creating a function that will create a new quote. The function will contain operations such as checking if the author exists and changing the style depending on the length of the quote. We will also be using the functions we created earlier, loading and complete.

- Create a new function called newQuote.
- Inside the function, call the loading() function.
- Create a new variable called `quote` that will pick a random quote from the apiQuotes array. `You will be using two functions from the Math module`
```
const quote = apiQuotes[Math.function(Math.function() * apiQuotes.length)];
//Where function is the name of the function from the Math module
```
- Create an if and else block where it checks if the Author field is blank. If it is, set the `textContent` of `authorText` with `Unknown`, else, set the textContent equal to `quote.author`.
- Create another if and else block which check if the length of the quote is greater than 120. If it is then operate `quoteText.classList.add('long-quote')`. Else, `quoteText.classList.remove('long-quote')`. This part is a little difficult so I will provide you with the code.
```
if (quote.text.length > 120) {
  quoteText.classList.add('long-quote');
} else {
  quoteText.classList.remove('long-quote');
}
```
- Set the quoteText (the variable we first initialized) equal to quote.text.
- Finally call the function complete().

**Get Quotes from API**


