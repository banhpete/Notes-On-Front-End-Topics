# Notes on Front End Fundamentals
This is by no means a comprehensive guide on Font End Fundamentals. Rather this is just a document with my notes to help understand/remember certain concepts.

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
