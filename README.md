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

**4. Get Quotes from API**

In this section, we will create an asynchronous function that will fetch the quotes from an external API, update the apiQuotes array, and then call the newQuote function. The code for this section will also be provided at the bottom of this section but try to do it yourself first!

- Create a new `asynchronus` function called `getQuotes`.
- Call the `loading()` function
- Create a new variable called apiURL and set it to this URL `'https://jacintodesign.github.io/quotes-api/data/quotes.json'`.
- Create a `try-and-catch` block.
- Inside the try block, create a new variable called `response` and set is equal to the await keyword and fetch the data from the apiUrl.
- Assign the apiQuotes variable to the actual JSON data which can be done with `await response.json()`.
- Call the newQuote() function.
- Put `error` inside the catch parameter and leave the block empty.

**Vocabulary**
1. Async Function (async):
- The async keyword is used to declare an asynchronous function. An asynchronous function returns a promise implicitly and allows the use of the await keyword within the function.

2. Loading Function (loading):
- This function is called at the beginning of the getQuotes function to show a loading spinner or perform any actions indicating that data is being loaded.

3. API URL (apiUrl):
- This variable stores the URL of the API from which quotes will be fetched.

4. Try-Catch Block:
- The try block contains the code that may throw an exception, and the catch block handles any errors that occur during execution.

5. Fetch API (fetch):
- The fetch function is used to make a network request and retrieve data. It returns a promise that resolves to the Response to that request.

6. Await (await):
- The await keyword can only be used inside an async function. It pauses the execution of the function until the promise is resolved. In this case, it waits for the fetch request to complete and returns the Response object.

7. Response (response):
- The response object represents the response to the request made by fetch. It includes information such as status, headers, and the actual data.

8. Response.json():
- The json method is called on the response object to extract the JSON data from the response body. This method also returns a promise that resolves to the parsed JSON data.

9. Await for JSON Data (await response.json()):
- The await keyword is used again to wait for the promise returned by response.json() to be resolved. This ensures that the apiQuotes variable is assigned the actual JSON data before proceeding.

**5. Tweet Quote (Optional)

In this section, you will learn how to tweet the quote but it is optional so free feel to skip.

- Create a new function called `tweetQuote`.
- Inside the function, create a variable called twitterUrl and set it equal to `https://twitter.com/intent/tweet?text=${quoteText.textContent} - ${authorText.textContent}`. You can find this in the official Twitter documentation.
- Open the window by calling the open function on window and set the parameters to the twitterUrl and 'blank'.

```
window.open(twitterUrl, '_blank');
```

**6. Event Listeners**

The event listeners will trigger the `newQuote` and `tweetQuote (optional)` functions when the respective buttons are clicked. Note that the tweetQuote button won't work if you don't finish section 6.

- Add an Event Listener to `newQuoteBtn` and set the parameters to `click` and `newQuote`.
- Add an Event Listener to `twitterBtn` and set the parameters to `click` and `tweetQuote`.

**Code block for getQuotes()**
```
async function getQuotes() {
    loading();

    const apiUrl = 'https://jacintodesign.github.io/quotes-api/data/quotes.json';

    try {
        const response = await fetch(apiUrl);
        apiQuotes = await response.json();
        newQuote();
    } catch (error) {
        // Catch Error Here
    }
}
```

Congrats! You have successfully completed the Generate Quote project! Make sure to save your work! 
