# Traversing the DOM

## Introduction

One feature that sets Javascript apart from other [scripting languages](https://en.wikipedia.org/wiki/Scripting_language) is its ability to select and manipulate HTML on a page through the DOM(Document Object Model). Even though the DOM was designed to be independent of any particular programming language, Javascript has fully gained preference as the language of the web. We can easily inject dynamic content into our web pages and create amazing effects with the power of the DOM.

In this article, we take a deep dive into some valuable methods exposed by the DOM API(Application Programming Interface) for selecting elements on a web page. This helps us to easily navigate our way through a webpage and get things done.

NB: If you are not sure what an API is, check out this [well-explained article](https://www.freecodecamp.org/news/what-is-an-api-in-english-please-b880a3214a82/).

## Prerequisites

This article was written with beginners in mind, only a basic knowledge of Javascript is required to follow through.

## A Refresher on the DOM

The Document Object Model offers a means of representing the content of a web page in a hierarchical way that makes it easy for programs to alter the styles, structure, and content. It's best to visualize the DOM in a tree-like form. Trees have stems, many branches, and uncountable leaves attached.

In the same way, a webpage usually comprises many elements nested and branched to one another. A simple illustration, say we have an HTML page:

```xml
<html>
    <head>
        <title>My title</title>
    </head>
    <body>
        <a href="#">My Link</a>
        <h1>My Header</h1>  
    </body>
</html>
```

The DOM structure would look like this:

![pic_htmltree.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1670952416841/Oto8KLwTc.gif align="center")

Image courtesy - [w3schools](https://www.w3schools.com/js/js_htmldom.asp)

## Traversing the DOM

`Traversing`, according to the Merriam-Webster Dictionary, means "to move back and forth or from side to side". And that is exactly what we seek to learn in this article. How do we move through the DOM tree and select the desired element(s) we need? Let's get right into it.

We can traverse the DOM in three directions:

*   Downwards
    
*   Sideways
    
*   Upwards
    

### Traversing Downwards

Traversing the DOM downwards often involves selecting descendants elements from a particular reference point. There are two major ways to traverse downwards which are:

1.  `element.querySelector` or `element.querySelectorAll`
    
2.  `element.children`
    

Let's see them in action.

```xml
<div class="container">
    <p class="text" id="first_text">Code</p>
    <p class="text" id="second_text">Eat</p>
    <p class="text" id="third_text">Sleep</p>
</div>
```

We have a container and some texts with unique ids but sharing the same class. Let's access some elements to illustrate downward traversing.

**element.querySelector()**

```javascript
const container = document.querySelector(".container")
console.log(container) 
//returns <div class="container">...</div>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671113699727/0Af7IZ9U3.png align="center")

**element.querySelectorAll()**

```javascript
const texts = document.querySelectorAll(".text");
console.log(texts); 
//returns a NodeList of all elements with class "text"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671106996101/khT8AXvid.png align="center")

**element.children**

```javascript
const container = document.querySelector(".container");
console.log(container.children); 
//returns a HTMLCollection of all children of the container element.
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671107274328/TBSiNm03p.png align="center")

N.B: To understand the difference between NodeList and HTMLCollection, kindly check out [this article.](https://medium.com/@layne_celeste/htmlcollection-vs-nodelist-4b83e3a4fb4b)

### Traversing Upwards

As you guessed, traversing the DOM upwards involves selecting the parent elements from a particular reference point in the DOM. There are two methods to traverse upwards:

1.  `parentElement`
    
2.  `closest`
    

Let's see illustrate them with examples.

**element.parentElement**

```javascript
const first_text = document.querySelector("#first_text")
console.log(first_text.parentElement); 
//returns the parentElement which is the container
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671114038159/eaR16qacP.png align="center")

**element.closest()**

`element.closest` gives us more control of upwards traversing. While `element.parentElement` selects only the immediate parent, we can go upwards multiple levels with the `closest` method.

> It traverses the element and its parents (heading toward the document root) until it finds a node that matches the specified [CSS selector](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors). - [mdn web docs](https://developer.mozilla.org/en-US/docs/Web/API/Element/closest)

```javascript
const first_text = document.querySelector("#first_text")
const closestContainer =  first_text.closest(".container")
console.log(closestContainer)
//returns <div class="container">...</div>
```

In this example, the search begins from `first_text` and continues upwards until a parent element with class 'container' is found and returned.

### Traversing Sideways

Traversing the DOM sideways involves selecting elements using their relationship with a reference element on the same level of the DOM. Easily referred to as Sibling elements. There are three methods to traverse sideways:

1.  `nextElementSibling`
    
2.  `previousElementSibling`
    

**nextElementSibling**

As the name suggests, this method helps us to access the next sibling element of a specified element. Let's get back to our use case.

```javascript
const first_text = document.querySelector("#first_text")
console.log(first_text.nextElementSibling) 
//returns the next element <div id="second_text ">...</div>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671116524371/T7Sz0vFwU.png align="center")

**previousElementSibling**

This does the exact opposite of the previous method, helping us select the previous sibling of a specified element.

```javascript
const second_text = document.querySelector("#second_text")
console.log(first_text.nextElementSibling) 
//returns the next element <div id="first_text ">...</div>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671116866837/lqadSGknE.png align="center")

### Recap:

1.  Traversing downwards
    
    1.  `element.querySelector`
        
    2.  `element.querySelectorAll`
        
    3.  `element.children`
        
2.  Traversing upwards
    
    1.  `element.parentElement`
        
    2.  `element.closest`
        
3.  Traversing sideways
    
    1.  `element.nextElementSibling`
        
    2.  `element.previousElementSibling`
        

## Conclusion

Practice makes perfect. Putting these methods to use in a Javascript project will help solidify what you have learned so far in this article. I encourage you to get your hands dirty writing code. Thanks for reading, cheers.

If you would like to reach me with comments, questions, or suggestions. Kindly drop a comment in the section below or send me a message on [Twitter](https://twitter.com/@iambenjamen)