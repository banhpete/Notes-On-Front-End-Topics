# Notes on Front End Topics
This is by no means is this a comprehensive guide on Front End Topics or a representation of my entire understanding of these topics and front-end development in general, rather these notes serve as just a way for me to build a general understanding of each topic. 

## What Can Google Chrome Developer Tools Do:
### March 28th, 2020
#### With CSS
Some of the things the Google Chrome Developer Tools can do with CSS are:
- Edit the styles right there on the page do tests.
- Take a look at the box element which is really helpful when you are trying to what margins, paddings, etc. you should use.
- See what CSS acutally are active or inactive on an element.

See guide from https://developers.google.com/web/tools/chrome-devtools/css/reference

#### With JavaScript
Some of the things the Google CHrome Developer Tools can do with JavaScript are:
- Determine if there is unused JavaScript similiar to determining if there is unused JavaScript. This is through coverage.
- Set breakpoints and follow through the code 
- Set conditional breakpoints so that the code can stop given some variable
- You can purposely call the debugger in your code by just writting "debugger"
- If an element changes and you want to see what happens, you can set a breakpoint on that element
- You can set a breakpoint on specfic AJAX source codes, for example, if you know somewhere in the code the incorrect URL is being called out, you can add a XHR breakpoint so that it breaks when the wrong URL code is called out
- When stepping through code:
  - Step over next function call: Executing a function without going into the function 
  - Step into next function call: When at a function call, you can actually step into it
  - Step out of current function: Leave the current function that you are currently inside
  - Step: Just step through every line

#### With Console
Some of the things you can do with the console are:
- Run Javascript as the console is also a REPL (Read–eval–print loop)
- There is a console api where you can use to send more than just simple console messages. For example there's a console.table where you can send a table to the console, and there's a console.error() to send an error message to the console.

See guide from https://developers.google.com/web/tools/chrome-devtools/console/reference

#### With Network
Some of the things Google Chrome Developer Tools can do with network are:
 - Throttle the page so that you can see how long it would take for a page to load on a mobile device. All you have to do is select a throttling option (Fast 3G, Slow 3G, Offline) and then empy cache and hard reload. 
 - Take screenshots while the page loads up to see how it looks like during the build up
 - Block certian resources to see how it changes page or how a page would look without the resource. 
 - View all the files loading, how long it takes to look, see the cookies, headers, etc. This could have been reviewed more but it is hard to find relevancy right now - review further later on.
 
 See guide from https://developers.google.com/web/tools/chrome-devtools/network/reference
 
#### To analyze performance?
Some of the things Google Chrome Developer Tools can do with the website performance are:
- Throttle the CPU so that you can test your website on low-end devices
- Record runtime performance to see data such how much time was used for rendering, scripting, painting, etc.
- See the fps at a given time of the website running
- There's more to this however it is hard to find relevancy right now - to review later on.

## General Web Development
### March 27th, 2020
#### What is Ajax?
AJAX stands for Asynchronous JavaScript and XML
To fully understand what Ajax is, it's importnat to understand how the web worked back in the early 1990s. All websites were based entirely on HTML pages. Anytime someone visited a website, it would be an HTML page that was requested and served, and anytime the website required to change, even for minor reasons, a new HTML page would need to be served, see the model on the left below.
![Model of a webapplication - From Wikipedia](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0b/Ajax-vergleich-en.svg/1024px-Ajax-vergleich-en.svg.png)
Obivously this was extremely inefficient, the website only requires a partial change but the whole page had to be reloaded. This is where a new set of web development techniques was developed in certain browsers which is now known as Ajax. This allowed us to code using Javascript to retrieve data from a server asynchronously (hence 'Aja' in Ajax) to receieve XML data (hence 'x' in Ajax) without disrputing the existing page. So we moved away from the model on the left and moved to the model on the right where servers were not just sending HTML files but data, and there was an additional "Ajax Engine" to coordinate what we were requesting from the server. There has been significant changes to these technologies since its developed, specifically JSON data is used more commonly now instead of XML but the name has stuck.

Some technologies include:
- The XMLHttpREquest
- Fetech()
- jQuery
- Axios 

So Ajax is not a language, or a library, rather it refers to technologies used in web development that allows browsers to send requets to a server in the background while a HTML page is being served or is served already. We often see these technologies in use on pages where changes are always happening like facebook, twitter, etc., and you are only one page. It was developed in certain browsers at first but has long flourished into a staple technologies for browsers.

See notes from https://en.wikipedia.org/wiki/Ajax_(programming) and https://en.wikipedia.org/wiki/XMLHttpRequest.

### March 28th, 2020
#### What is a code linter?
Essentially, it is a tool that goes through your source doe to flag any errors, bugs, etc.

In visual studio code we use ESLint for to analyze Javascript.

These are important for interpreted languages (i.e Javascript or Python) which do not have a compiling phase like C.

See notes from https://en.wikipedia.org/wiki/Lint_(software)

## HTML
### May 13th, 2020
#### Links
In HTML, we use href, or src, to reference files or images that is external to our HTML file so that we can use them in our HTML file. For example:
```
<head>
  <meta charset='UTF-8'/>
  <title>Hello, CSS</title>
  <link rel='stylesheet' href='styles.css'/>
</head>
```

Now the question is how are we supposed to call out the file/image? There three wayss of writing them, absolute links, relative links and and root-relative links. 
  - **Absolute Links** you use for files/images from a web resource. This you will use the entire link starting with "http:/".
  - **Relative Links** you use for internal files/images. It uses the path of file/image relative to the HTML file itself. So if the file you want to call out is in the same folder as your HTML file, for href or src, you just need to write the name. If it's in another folder, you have to navigate the directory. We use ".." to navigate outside of the folder that the HTML file is currently in. 
  - **Root-Relative Links**, which is sort of similiar to relative links but is relative to the root of the entire website. You only really use this when you have a web server. Root relative links require a slash in the beginning '/'.
  
  **Differntiating between Relative and Root-Relative:** Think of if this way, when you don't provide "." or "..", we don't know what path to use, so we use the closest one we know, the root. If we do provide "./" then we know the path as the "./" means "this folder". Just think when we are using terminal commands and we use "-ls". This shows "./" and "../" as ways to interact with the folder internally and externally.
  
#### Character Sets
To render special characters in your HTML include:
```
<meta charset='UTF-8'>
```
In the head section.

### May 15th, 2020
#### Semantic HTML
Semantic HTML is the idea that HTML is created in a way where the content is arranged in a meaningful way with intuitive HTML elements such as article, aside, figure, footer, header, etc. This has become more important in the last few years as this makes the website more accessible, especially to those who need to use screen readers, and also because of search engine optimization.

Some important things to consider are:
 - h1 is usually used as the top-level banner
 - Articles should be made such that an app can be able to grab it from your website and it will still make sense to readers. This is important for search engine optimizations. Consider it the perfect element for a blog post.
 - The date element will allow google to include it in their search engine, this is pretty important to have.
 - Figures are good to be used with images so you can include figcaptions, this also can be an alternative to using'alt' in images.
 
 See this [link](https://www.internetingishard.com/html-and-css/semantic-html/) for more information.
 
## CSS
### October 27th, 2019
#### Why do we use the "before"?
Based on my experience so far - we use the pseudo element before to add content before an element. W3 does a great example of showing how "before" works: https://www.w3schools.com/cssref/sel_before.asp.
Another great example of using the "before" pseudo element is here: https://codepen.io/banhpete-the-bold/pen/RwwVwPW. What happened here is that the "before" pseudo element was used to insert a background picture before the body tag instead of inserting the background into the body tag itself. This was done so that we can set an image as a background for the whole page and have it fixed such that when we scroll through the page, we only scroll through the contents of the body tag and not the background (see the codepen). If the background picture was inserted into the body this could not happen because - we need to have the image fixed not the content of the body!

### May 13th, 2020
#### Vertical Margin Collapse
We need to keep in mind that when we have two boxes, one on top of each, the bottom margin of the top box, and top margin of the bottom box will not persist. The bigger margin out of the two will continue to exist while the smaller one will "collapse". So if the bottom margin of the top box is "50px" while the top margin of bottom is "25px" the two boxes will not be separated by 75px, but rather just 50px.

To work around this we can but an invisible element inbetween, like so:
```
<p>Paragraphs are blocks, too. <em>However</em>, &lt;em&gt; and &lt;strong&gt;
elements are not. They are <strong>inline</strong> elements.</p>

<div style='padding-top: 1px'></div>  <!-- Add this -->

<p>Block elements define the flow of the HTML document, while inline elements
do not.</p>
```

#### Inline Margins
For inline elements, remember that when using the margins, there are no margins for the top or bottom, just the left and right. This is because it's **INLINE**, the element needs to say **IN** **LINE**.

#### Centering Block Elements
Recall that text-align property will do nothing for centering a block element, it's really only for the text in the element. To center a block emenet we need to use magins, floats, or have a flexbox. Having margin as "auto" will usually do the trick. 

#### Restting Styles
Different browsers have different default styles, that's why it's a good idea to override default styles and add:
```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```
This resets all the styles. Box-sizing as border-box will ensure that when you set width or height, it is exactly that size. Without setting this, when you set the width, it includes the border, padding, etc; it's not accurate.

### May 14th, 2020
#### Linking CSS
When linking CSS Files, recall that the order that you call them in determines which spreadsheet overrides which. In general the later the style shows up, the greater the priority - this is way inline style always overrides everything else. Inline style would be called the latest as it's part of the HTML elements, where style is almost called first since it's part of the head.

### May 15th, 2020
#### Floats
Before Flexbox and Grid existed, Floats were the main way to design web layout, and while it has become more or less obsolete with most web developers it's still definitely worth learning due to the fact that it was so widely used.

To turn on float for an element, we set the css property "float" to "left" or "right". By default, float is set to "none".

What float does to an element (specifically a block element), is that it makes all the elements surrounding it flow around it. The float will be placed depending on where the last block element was, and other block elements will be placed underneath it.

Refer to this [link](https://www.internetingishard.com/html-and-css/floats/) for examples and more information.

Somethings to consider with floats:
 - When there are floats inside a parent element, they will not contribute to the the total height or width of the element. Instead they will just overflow out of the parent element. To prevent this, we need to give the css element the style property "overflow:hidden" which basically tells it that overflow is not alloweed. This will cause the parent element to consider the overflowing element as when it is trying to determine width and height. You can also use this when you don't want the text inside an element to flow around (see the end of the article above).
 - When there are other elements inside a parents element along with the float elements, the other elements will flow around the float element. To have the other elements consider the floats when they are being placed, we need to give the other elements the style property "clear:both". This will cause the element to consider the placement of a float.

### May 18th, 2020
#### Shadows
When adding a shadow to box element, a common pattern is to have it such that the short property looks like the following: 
- 5px 10px 20px -20px;
- When creating box shadows, just remember that the shadow starts off as a simple square underneath a box. The first two values controls the position of this secondary box. The third value controls the blur and fourth value controls the spread.

#### Notes on Flexbox
Flexbox is a styling model that provides an efficient way to layout, align and distribute space among elements within your document. A source of information on flexbox can be found here at this [link](https://www.freecodecamp.org/news/understanding-flexbox-everything-you-need-to-know-b4013d4dc9af/). 

Essentially, when you using the flexbox model, we need to to first give a container "display:flex" to make it a flex container, and the elements inside become a flex items. When these elements become a flex item they inherit the flex behaviours which make it easy to align or distribute within a space. Flexbox essentially replaces floats.

When taking a flexbox approach, remember that a flex item can also become a flex container. This is nicely visualized in the section "Building a Music App Layout with Flexbox" in the link mentioned above. Take a note on how the author has one flex container, with two inner flex containers, and then each other container has its own flex containers.

Some other notes on the Flexbox:
- Flexbox has two important axis to consider, the main axis and cross axis. Flex-direction determines the main axis and the cross axis. A flex-direction of column will have the main axis vertical and the cross axis horinzontal. 
- There are two types of properties with Flexbox, properties that affect the flex-container, and the properties that affect the flex-items
- Flex-grow affects flex items. This determines how much an item grows when there is white space in the flex-container. By default, the flex grow is set to 0 so it will never grow.
- Flex-basis affects flex items. This determines the initial size of the flex item in the main axis before growth or shrinking. Alternatively, you can set the size and never have it grow or shrink.

### May 19th, 2020
#### Using Advance Positioning to Create a Popup Menu
See guide [here](https://www.internetingishard.com/html-and-css/advanced-positioning/) for further details. 

Essentially, we need to take advantage of the two properties:
```
  position:relative;
  position:absolute;
```
To make a pop up menu for an item on the nav bar we need to position the sub-items within the item element. Take for example:
```
      <ul class="menu">
        <li class="dropdown">
          <span>Features &#9662;</span>
          <ul class="features-menu">
            <!-- Start of submenu -->
            <li><a href="#">Harder</a></li>
            <li><a href="#">Better</a></li>
            <li><a href="#">Faster</a></li>
            <li><a href="#">Stronger</a></li>
          </ul>
          <!-- End of submenu -->
        </li>
        <li><a href="#">Blog</a></li>
        <!-- These are the same -->
        <li><a href="#">Subscribe</a></li>
        <li><a href="#">About</a></li>
      </ul>
```
The nav item will have position relative, and the submenu container (class="feature-menu" in the case above) must be absolute such that is positioned relatively to the position relative. Once placing it in the right place we need to make it hidden until activated.

## JavaScript
### May 11th, 2020
#### Adding Event Handlers to an Element
Using Javascript by itself, it is recommended to add events two ways:
- Using Event handler properies, such as onclick, onfocus, onblur, onmouseout, etc. This involves selecting the element with Javascript, and then modifying the event handle property to call out a function name OR have an anonymous function.
```
const btn = document.querySelector('button');

function bgChange() {
  const rndCol = 'rgb(' + random(255) + ',' + random(255) + ',' + random(255) + ')';
  document.body.style.backgroundColor = rndCol;
}

btn.onclick = bgChange
```
- Or we can use addEventListener() which does provides the advantages of adding multiple events handler to an element. Using the Event Handler Properties only allows for one eventhandler at an element. We can also use the removeEventListener() to remove an event handler.

#### Event Objects
Event Objects are these objects that are created when trigged by an user action or an event. These contains properties and methods that are common to all events, which tell you more about the event that occured. These event objects are passed into event handlers as soon as the event listeners detect them and determine they are the event they are looking for.

#### Preventing Default Behaviour
In the situation where you want to prevent an event from doing what it does by default, you can call the preventDefault() function on the event object. One example you want to do this is with form submission. By default, when the submit button is clicked the data is to be submitted to a specified page automatically. To prevent this behaviour we need to access this event, we do so by adding an event handler for form submissions, and call e.preventDefault();

#### Event Bubbling
When an element has a parent element, and it triggers an event, what happens is that:
- The browser checks if the element has an event handler registered for the event, if it does it runs
- The browser then checks the next ancestor element and does the same thing, and then the next one, and the next one, etc.
We need to be conscious of this as it could really mess up our original intentions. 
- To prevent this we call the stopPropagation() function on the event object at one of the event listener. This will tell the browswer to stop at this event listener, don't look into futher elements.

#### Event Delegation
Because we know event objects bubble through the ancestral elements, we can take advantage of this to make our coding a little easier. If you have a parent element with several children element that you want the same event handler on, you can just have the parent element with the event handler. All the events that are triggered will bubble up to the parent and at that point we can handle them.

### May 18th, 2020
#### Javascript Runtime Environment
The Javascript Runtime Environment is the environment that which the Javascript Engine works in, where there are several features that works along side with the Javascript Engine to run the JS code from a web application. See the following picture:

![Visualization of the JavaScript Runtime Environment](https://miro.medium.com/max/1400/1*zeKjWCjyAGZ9JN4fvnWsiA.png)

So the JavaScript Engine, overly simplified, has two parts, the memory heap and the call stack. The memory heap stores the variables and functiosn declared in the JS code. The call stack, is essentially where actionable items from the JS code is stored in to await the Javascript Engine to parse. Keep it mind that the JS engine is single threaded meaning it does everything synchronously, one action at a time. 

Now the Javascript Runtime Environment provides WEB APIs such as the DOM tree which allows you to interact with the HTML, and AJAX to allow you to do asynchronous operations. To work with asynchronous operations, the event loop and callback queue are also provided by the Javascript Runtime Environment. After an asynchronous Web API operation is called by the Javascript Engine, rather than the call stack waiting for the some values to return, the callback queue will await the data to return instead and it will store the function to run once that data does return, this function is called the callback Function.

Once the data does return, these callback functions are not invoked immediately, in the end it still needs to the JS Engine and it will only invoke when the call stack is free. Therefore the event loop exist to check both the callback queue and the stack to ensure that when there is a callback function waiting, the call stack will run it through JS Engine as soon as possible.

### June 6th, 2020
#### Classes
Like most object oriented programming, JavaScript also has classes. Classes are essentially a blueprint of an object, to understand what they are, let's look into the following example.

Say for example we have some application that has a bunch of different data on different people, to organize the data, a good approach would be to put data belonging to a specific person into their own object. Now we know we can use object literal syntax to create the objects for each person but that takes a lot of time to write over and over, and not only that, it's extremely repetitive. That's where classes come in, they define how a specific object should look, and then we can create instances of the class (objects based on this template) for each person.

Now the definition of a class is essentially what properties and methods a class should have. Here is how they are defined:
```
 class Vehicle {
   // the constructor will always be called
   constructor(vin, make, model) {
     this.vin = vin;
     this.make = make;
     this.model = model;
     this.running = false;  // default to false
   }
   start() {
     this.running = true;
     console.log('running...');
   }
 }
 ```
 The properties are defined in the constructor, this is the function that is called when an instance of the class is created to define the properties of that instance - it constructs it. Methods, which are just functions of a class, are just declared with the name, parentheses, and then the function's code.
 
 Now it's important to note that there are two different types of methods:
  - Static methods are the methods that are called on the class itself and not on the instance. Static methods are used to implement behavior that does not pertain to a particular instance, but is related to the class itself. It doesn't use any values within an instance. These functions are made in a class by writing the method and having static added before the method.
  - Prototype methods are called on the instance itself

To create an instance of a class, we use the keyword "new". See the following:
```
 let spyPlane = new Plane('secret', 'Lockheed', 'SR-71', 'USA');
```

Now when we create a class, we can inhereit properties and methods from another class, this essentially makes our new class a subclass of a superclass. **Why would we want to do this?** So we can add additional properties and methods to a class, but we only want to use this class for specific situations. For example, if we have an insect class, we can create the subclasses Bumblebee and Grasshopper, which extend the class of insect further and add additional properties and methods that are specific to those subclasses.

To extend a class/create a subclass:
 - We write "class" and then the subclass name, and then we add "extends <class>" which is to say that this sub class is an extension of this superclass. 
 - Like any class, it needs to have a constructor to *construct* the properties. In this property, we need to make sure to add "super()" and pass in the arguments needed for the super class. Think of this keyword as the way we commnuicate with the superclass.
    - The "extends <class>" alone doesn't do anything, it just gives us access to the superclass but we need to specifically mention in the constructor that we need to run the superclass constructor as well, hence "super()".

### June 8th, 2020
#### Handling Asynchronous Operations
Now the most traditional ways of handling asynchronous operations, such as an third party api call, has been with callback functions, a function that is "called back" once the asynchrous operation is completed. This callback function is usually called as a parameter in the asynchronous operation and while it works it does have its downfall. For example, given some API, we may need to use multiple endpoints to get the information we need, so we do  multiple asynchronous calls after one another, this leads the nesting of callbacks, and what people now call **Callback Hell**. It worked! But it never looked pretty. This lead to the development of the promise object.

##### Promises
Now the promise is an object that thas three sates, *pending, fulfilled, rejected*. Once a promise is created or is called, it will immediately assume a state of pending, and will wait to be fulfilled or rejected. Once it is fulfilled, the promise can be actioned by appending ".then()" and then passing in a function.

To become fulfilled, it needs to run a resolve function, or if there was some sort of error in the promise, it runs a reject function, these functions are passed as parameters of another function that is passed in a new promise, for example:
```
 const p = new Promise(function(resolve, reject) {
   let value = 42;
   if(value > 41) resolve(value);
   reject(value);
 });
 
  p.then(function(result) {
   console.log(result);
 }).catch(function(err){
  console.log(err);
 }
 ```
So in the example above, we create a new promise and this is assigned to the const p, this will have a state of pending right away. When we create a new promise we pass in function(resolve, reject). The function will run resolve with certain conditions and reject in certain conditions to change the state of the promise. If it runs resolve, we can then run the function in the "then()", or if it rejects, we run "catch()".

**Now what does have to do with anything with asynchronous actions??**
A promise essentially serves as a wrap for asynchronous operations. Essentially, we create a promise, and we call an asynchronous operation which will have a callback function to call resolve or reject depending on what is returned. For example:
```
const p = new Promise(function(resolve, reject) {
  someAsyncOp(someData, function(data){
    if(condition for data){
      resolve(data)
    }else{
      reject(data)
    }
  }
});
```
This way, instead of dealing with the asynchronous operation with a callback, we can write:
```
p.then(function(){
  some actions
})
```
Now writing one promise alone does not really show the advantage of promises over callbacks. The advantages of promises shine when you have multiple asynchronous operations, rather than having multiple callbacks and having callback hell, we instead write promises and chain them such that one promise completes, it returns another promise, and that way **we just have multiple .then() rather than multiple callbacks*. 

Then we also have promise.all which even ties multiple asynchronous operations together so we can call them simultaneously, and we only run .then or .catch when they both resolve, or if one of them reject. Fpr example:
```
const p1 = new Promise(...)
const p2 = new Promise(...)
Promise.all([p1,p2]).then(...)
```
Promise.all accepts all promises in an array, and it essentially combines the promises to make one big promise!

**Now we may think that writing asynchronous operations as a promise is a pain though but luckily many asynchronous operations now actually return promises, so most of the time we, as developers, just need to write ".then" or ".catch" to determine what we want to do with the promise"**

#### Async/Await
Now that we know about promises, we can also start talking about async/await, another way of working with promises which is considered syntactic sugar because it makes working with promises easier and better to read, **essentially, we're making asynchronous code look like synchronous code**.  

To use async, we write "async" before any function making it an asynchronous function, what this means is that the function will first return a promise when it is first called, and will resolve when the function makes a return itself. Now in this function we can essentially write "await" before any promise and this will cause the javascript engine to pause at this line of cause until it is resolved **(making it synchronous!)**. See for example:
```
 async function printUsers() {
   const endpoint = 'https://jsonplaceholder.typicode.com/users';
   let users = await fetch(endpoint).then(res => res.json());
   console.log(users);
 }
 
 printUsers();
```
We will pause at the fetch() until it is resolved, that way we actually console.log actualy data, not ust a promise.

**Now, while it's nice to make code synchronous for us to better comprehend each step, if everything was synchronous, the advantages of JavaScript's asynchronous programming is quickly lost, this especially apparent with multiple promises.** But there is no worries, as we can use async/await to handle multiple promises. We can construct all our promises first, and call await on the promises after when we need the results! For example:
```
async function concurrent() {
 const firstPromise = firstAsyncThing();
 const secondPromise = secondAsyncThing();
 console.log(await firstPromise, await secondPromise);
}
```
Basically we're saying, "Here are two promises - don't use them until they're resolved"

Now with promises, we handled error's with ".catch()" but with async/await, how do we handle errors now? Well, in the async function, we can write all of the asynchronous operations, and whatever other operations you may expect an error in an try and catch block. For example:
```
async function test(){
  try{
   promises...
  }catch(err){
    actions to take if errors are found during the code in the try block
  }
}
```
### July 19th, 2020
#### this
The keyword 'this' is a pre-defined variable inside **every** function in JavaScript, and it provides function with an object. Usually JS will set the value of this to the object that the function belongs to (as you might guess, this means 'this' is a very much related to object oriented programming language"), but a user may explicitly set the value of this as well.

As a result of 'this', it allows functions to access the properties and methods of an object inside of it and for efficient code reuse, for example consider the constructor in a class. We use 'this' to reference the class, and this allows for every instance made from this class to have its own instance of properties.

So let's explore the different types of functions, and what 'this' will reference:
- In a non-method Function, 'this' will just reference the window. If 'strict mode' is set, it's just undefined.
- In a method, 'this' is bound to the the object that calls the method, the ruler is: The object left of the dot is what 'this' is bound to.
- In a class, it references 'this' to the new shiny object that is created
- Arrow functions are set to the context of its **enclosing function** or the global object (window) if there is no enclosing function.

We can explictily set this using call, apply, and bind. However this can not be used for arrow functions. 

### July 26th, 2020
#### import/export
The import and export syntax allows us to take a modular approach when writing JavaScript files. 
 - When we import items from a module, if we don't use curly brackets, we import the default item being exported. To import items that are no the default item, we use the curly brackets, and we have to specify the actual name of the item.
 - When we are exporting, we can specify what is the default item being exported, and then everything else we have to export an object of items OR we can just inline export on every item we want to export.

Now import and export are a part of es6 and unfortunately it's not really supported in browsers therefore when we use import/export in react apps (because we need to write components which is modular) we have to use babel (tooling). 
