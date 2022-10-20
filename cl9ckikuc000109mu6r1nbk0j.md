# What is Event Delegation in Javascript?

## Summary
In this article, I explain and illustrate a very useful concept in Javascript - `Event Delegation`.  An understanding of Javascript Fundamental concepts such as variable declaration, control flow, Array methods, and DOM (Document Object Model) manipulation is required to follow through with the article. 


## Introduction
Javascript remains the preferred programming language of the web for many reasons, one of these reasons is its ability to directly manipulate the content on the client (web browser) through the DOM Manipulation APIs. With the power of DOM manipulation, creating dynamic content on the web is considerably easier. 

### Events and Event Listeners
Events are expected actions on a webpage, sometimes triggered by user actions. Examples of events include clicking on an element, mouse entering or leaving an element, form submitting, and many more. JavaScript can listen for these events and trigger certain actions when the events occur. That is the concept of event listeners, basically functions awaiting some events to be triggered.

Let's see a simple example of how Javascript can directly manipulate static content (HTML) through event listeners.

%[https://codepen.io/iam-benjamen/embed/preview/bGMJBPo?default-tab=html%2Cresult&editable=true&theme-id=dark]

We add a click event listener method to the button that triggers a callback function, altering the background color everytime the button is clicked. Pretty simple, right?  Feel free to play around with the Javascript code! Let's get into `Event Delegation` proper.

## Event Delegation
What happens when we have to attach an event listener to many elements at once? Surely, it doesn't make sense to attach the functions to each of them seperately. Event Delegation is a code pattern that helps to handle dom manipulation in a batch. A proper definition:  *Event delegation refers to the process of using event propagation (bubbling) to handle events at a higher level in the DOM than the element on which the event originated*.

#### What is Bubbling?
The Bubbling concept is quite simple. When an event is fired on an element - the handlers are first run on it, then on the immediate ancestors of that element, up till the document object.  Consider the example below, when a click event is triggered on inner `P` element - it propagates to its parents. `click on the p box for demonstration`

%[https://codepen.io/iam-benjamen/embed/preview/mdLgWVK?default-tab=result&editable=true&theme-id=dark]

Almost all events in Javascript exhibit this behavior, with the exception of very few like the `focus event`.

**event.target()**: This method is used to obtain the element that dispatched a certain event. Keep it in mind, it plays a crucial role in event delegation as we will soon practice.

### Event Delegation in action
The event delegation pattern works by `adding the Event listener to the common parent of the elements` and `determining what element originated the event using event.target()`. Say we have three buttons instead of the single one we had in the previous example.
```
<!DOCTYPE html>
<html>
   <body>
       <div class="button_container">
            <button class="colored_button">
                  I'm colored red
            </button>
              <button class="colored_button">
                  I'm colored red
            </button>
             <button class="colored_button">
                  I'm colored red
            </button>
      </div>
  </body>
</html>
```
Let's use to event delegation to attach a click event to them all.
```
const button = document.querySelector(".colored_button");
const button_container = document.querySelector(".button_container");
let current = true;

//Event handler function
function handleClick(e) {
  const clicked_button = e.target;
  if (current) {
    clicked_button.textContent = "I'm colored blue";
    clicked_button.style.backgroundColor = "blue";
    current = !current;
  } else {
    clicked_button.textContent = "I'm colored red";
    clicked_button.style.backgroundColor = "red";
    current = !current;
  }
}

//Add Event handler to the parent element
button_container.addEventListener('click', function(e){
  //determine where the event originated from
  if(e.target.classList.contains("colored_button")){
    handleClick(e)
  }  
})
```
Remember, the two steps are:
1. Add Event handler to the parent element
2. determine where the event originated from using `event.target`

Now, let's put it all together and see the result. 

%[https://codepen.io/iam-benjamen/embed/preview/eYrovLv?default-tab=html%2Cresult&editable=true&theme-id=dark]

Amazing, right? A single event listener function serving all three buttons at once!

## CONCLUSION
Hopefully, you have gained a more robust understanding of Event delegation through this article. In the next article, we willl implement tabbed components using the event delegation pattern. Do well to bookmark this article and follow me for updates. 
Thank you for reading. Your comments and suggestions are most welcome. Cheers! 