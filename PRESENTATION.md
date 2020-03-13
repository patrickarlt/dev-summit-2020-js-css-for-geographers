<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

## Allison Davis (1)

---

<!-- .slide: data-background="./img/2020/devsummit/bg-1.png" -->

<h1 style="text-align: left; font-size: 80px; margin-top: -90px;"><b>JavaScript</b> and <b>CSS</b> <i>for Geographers</i></h1>
    <p style="text-align: left; font-size: 1.5em;">Patrick Arlt, Allison Davis & Nate Bedortha</p>
    <p style="text-align: left; font-size: 1.5em;">Slides: <a href="http://bit.ly/2PLJft4" style="font-family: monospace;">http://bit.ly/2PLJft4</a>

<aside class="notes">
(Allison, Nate, Pat)

@TODO verify names and slide link

</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-4.png" -->

## This talk is all fundamentals.

<aside class="notes" data-markdown>
(Allison)
* This is a very quick introduction to the fundamentals of web development - HTML, CSS, and JavaScript
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-3.png" -->

## First, Some Notes

Lots of supplemental info in these slides.

Designed to help you keep learning beyond this talk.

Pretty much everything is a link.

Slides: <a href="http://bit.ly/2PLJft4" style="font-family: monospace;">http://bit.ly/2PLJft4</a>

<aside class="notes" data-markdown>
(Allison)
* this is a lot to cover in a very short amount of time
* so don't worry if things don't make sense right away
* this talk is designed to be used as a resource for future learning
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-3.png" -->

## Web Development is Hard

- It's ok to feel overwhelmed
- Good news: you're more equipped than you think!

- Scripted with ArcPy?
- Scripted with Python?
- Configured an app?
- Used Arcade?
- Used Model Builder?

<aside class="notes" data-markdown>
(Allison)
* Technical knowledge from GIS translates very well to web development
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-3.png" -->

## A quick note on web servers

- HTML, CSS, and JS all go in your web server

- [How to set up a local web server](https://gist.github.com/jgravois/5e73b56fa7756fd00b89)

- Install [Node](https://nodejs.org) > Terminal/Command Line/Windows Bash/Powershell

```bash
npx http-server .
```

- For fast prototyping use [CodePen](https://codepen.io) or [StackBlitz](https://stackblitz.com/)

<aside class="notes" data-markdown>
(Allison)
* Using a web server doesn't necessarily mean you're serving pages on the internet for all to see.
* You can use a local web server to load your own static files
* Not comfortable on the command line? There are tons of great free resources online. Links to some in the resources slide
* In a hurry? Use a web tool like CodePen for prototyping - there are lots of options
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-3.png" -->

## HTML

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Hello!</title>
    <!-- <link> (CSS) goes here -->
  </head>
  <body>
    <!-- Content (more html) goes here -->
    <h1>Welcome</h1>
    <div>Here's some unstyled content.</div>
    <!-- <script> (JavaScript) goes here -->
  </body>
</html>
```

- [Try it in CodePen](https://codepen.io/araedavis/pen/eYNeBXo)
- [MDN's HTML docs and guides](https://developer.mozilla.org/en-US/docs/Web/HTML)

<aside class="notes" data-markdown>
(Allison)
* Here's a basic html document
* The title is what you see in title bar of the browser
* Title and link tags go inside the head tag
* Content goes inside the body tag
* Script tags (JavaScript!) as a rule go at the end right before the closing body tag
* But why? The page loads in order. So, if a bunch of HTML loads before your CSS - unstyled HTML! If a script is loading before all your HTML and CSS, your page will be blank and appear blocked - bad user experience!
* There's a lot more to HTML - recommend checking out MDN's guides and documentation for further reading

- Hand off to Nate

</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

## Nate Bedortha (2)

---

<!-- .slide: data-background="./img/2020/devsummit/bg-4.png" -->

## CSS

<pre style="font-size: 125%;"><code class="ss">html, body, #map {
  margin: 0;
  width: 100%;
  height: 100%;
}</code></pre>

<aside class="notes">
(Nate)
CSS is a language for specifying how HTML documents are presented to users — how they're laid out, what typefaces they use, and what colors different elements should be.
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

### Where does CSS go?

- Inside a `.css` file that is loaded with a `<link>` tag.
  ```html
  <link href="my-css-file.css" rel="stylesheet" />
  ```
- Inside a `<style>` tag.
  ```html
  <style>
    /* Put CSS here*/
  </style>
  ```
- Inside an element’s `style` attribute. ⚠️
  ```html
  <p style="color:blue;">Blue text!</p>
  ```

<aside class="notes">
(Nate)
Where do we put CSS?
A CSS file, referenced by a link tag is the most common place; that way many HTML documents can reference the same CSS document.

You can also style a single document directly by using the style tag inside the documents head.

And as a last resort, you can put CSS inside an elements style attribute.

</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

### What does CSS look like?

<pre style="font-size: 125%;"><code class="ss">html, body, #map {
  margin: 0;
  width: 100%;
  height: 100%;
}</code></pre>

<aside class="notes">
(Nate)
This is a single CSS Rule, it's made up of Selectors, and sets of properties and values.
Selectors "select" the elements inside the document, in this case the html tag, the body tag, and an element with the ID "map"
Properties are Identifiers that indicate an elements specific stylistic features; here we're going to change the margin, width and height.
Then Each property is given a value that indicates your changes to that feature, in this case, 0 and 100%.
Style sheets are made up of many rules that are read in order. At the end of the document, the browser cascades every element's rules together and shows it to the user.
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

## The "C" is for Cascading<p>

Styles _cascade_ into the final styles for the HTML elements that match their selectors.

- Browser and user styles
- <code>&lt;link rel="stylesheet"&gt;</code>
- <code>&lt;style&gt;</code> tags
- Style attributes <code>&lt;div style="..."&gt;</code>

<aside class="notes">
(Nate)
Let's take one step back and talk about the "C"; The "C" is for "Cascading".
The browser loads CSS in a specific order: Browser defaults, then linked stylesheets, followed by style tags and style attributes.
The order of the rules matter: the last rule in the source wins.
Since the rules come from different places, you could be setting the same property to different values… that's where Specificity comes in.
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

### CSS Specificity

When properties collide specificity determines which property wins.

1. Rules with `!important`
2. Inline styles `<div style="...">`
3. `<style>` and `<link>` tags
4. Selector specificity
   1. `#id-attribute` - &lt;div id="..."&gt;
   2. `.class-attribute` - &lt;div class="..."&gt;
   3. `div` - &lt;div&gt;

<aside class="notes">
(Nate)
When properties collide specificity determines which property wins.
Each type of selector is more *specific* than the next.
An ID selector can only match one element.
A class selector can match different element types.
An element selector matches all elements!
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

### Let's inspect some CSS

Right click on something you want to change click "Inspect Element"

[Explore a Storymap](https://story.maps.arcgis.com/apps/Cascade/index.html?appid=46daf1304a0c4ad69a8935c7ed2ab692)

<aside class="notes">
(Nate)
A crucial tool when writing CSS is your browser's Developer Tools, which allows you to modify any CSS and see the results instantly.
For example, this Story Map is beautiful, but we've been asked to really make this design sing. Let's change the color of this text box and see what we come up with.
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-6.png" -->

## Let's Build an App!

<img src="app.png" alt="A Simple Mapping App" style="border: none; background: transparent; box-shadow: none;">

<aside class="notes">
(Nate)
We've got a great idea for a web app: a map that displays the locations of non-gasoline alternative fueling stations.
How do we build it?
First we'll need to think about the layout… it looks like our design has two major components: a box for text information, and a box for our map.
We can write some HTML to put these components on a page, but how can we move these boxes where we need them to go? We can use the "display" property.
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

<h2><a href="https://codepen.io/oknoway/pen/KKpyMJK?editors=1100">Block</a> vs <a href="https://codepen.io/oknoway/pen/GRJOqLY?editors=1100">Inline</a></h2>

<ul>
  <li><a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements">Block-level elements</a></li>
  <li><a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements">Inline elements</a></li>
  <li><a href="http://learnlayout.com/display.html">Learn CSS Layout: the "display" property</a></li>
  <li><a href="https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Normal_Flow">Normal Flow</a></li>
  <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout/Block_and_Inline_Layout_in_Normal_Flow">Block and Inline Layout in Normal Flow</a></li>
</ul>

<aside class="notes">
(Nate)
By default all elements have a display value of *block* or *inline*. You can kind of guess what they do by the names, but let's look at some examples:
Block elements are laid out out one after the other, vertically, beginning at the top of a containing block. Most of their dimensions can be changed with different CSS Properties
Inline elements are laid out horizontally, one after the other, beginning at the top of a containing block. Since these elements are "in line" with each other, most of their dimensions can't be changed.
And while we're talking about dimensions, this is the perfect time to mention Units.
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

<h2><a href="https://codepen.io/oknoway/pen/BaNmLQX?editors=1100">Units</h2>

<ul>
  <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length">Full unit reference</a></li>
  <li><a href="https://css-tricks.com/the-lengths-of-css/">The Lengths of CSS</a></li>
  <li><a href="http://www.quirksmode.org/css/units-values/">Unit and Values - QuirksMode</a></li>
  <li><a href="https://www.youtube.com/watch?v=_sgF8I-Q1Gs">📺 Layout Land: Introduction to Viewport Units</a></li>
</ul>

<aside class="notes">
(Nate)
There are lots of different units, but usually we're talking about length units. Length units can be either Absolute or Relative.
Absolute length units represent an actual physical measurement: pixels, inches, or centimeters.
For a long time, we used pixels for every length, but as viewport sizes change, and designs needed to become more flexible, we needed:
Relative length units represent a measurement in terms of some other distance:
the size of a specific character or the line-height of a font, or the size of the viewport.
Okay, quick detour for some basics, and now we're ready to layout our App UI. To do that, let's look at a layout model called Flexbox.
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

<h2><a href="https://codepen.io/oknoway/pen/vYOWXjM?editors=1100">Flexbox</a></h2>

<ul>
  <li><a href="http://flexboxfroggy.com/">Flexbox Froggy</a></li>
  <li><a href="http://learnlayout.com/flexbox.html">Learn CSS Layout: flexbox</a></li>
  <li><a href="https://css-tricks.com/snippets/css/a-guide-to-flexbox/">A Complete Guide to Flexbox</a></li>
  <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout">MDN: CSS Flexible Box Layout</a></li>
</ul>

<aside class="notes">
(Nate)
Flexbox is a layout model that's optimized for UI design.
Flexible boxes layout their children along one dimension: either horizontally or vertically.
Flex children can "flex" their size to grow or shrink without overflowing their parents.
In this demo, you can see the map element is always growing at twice the rate of the sidebar.
This gives us a lot of control over our page layout, but sometimes we need to position things a little more specifically. For that we use the position property.
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

<h2><a href="https://codepen.io/oknoway/pen/OJVObgW?editors=1100">Positioning</a></h2>

<ul>
  <li><a href="http://learnlayout.com/position.html">Learn CSS Layout: position</a></li>
  <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/position">MDN: position</a></li>
</ul>

<aside class="notes">
(Nate)
The Position property allows elements to be positioned in a document, relative to other elements.
We can use it to overlap elements over one another.
Notice in this demo we've positioned four different widget elements over our map element.
Flexbox + Position allows a lot of layout options, but for even more control, we need CSS Grid Layout
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

<h2><a href="https://codepen.io/oknoway/pen/JjdORQw?editors=1100">Grid Layout</a></h2>

<ul>
  <li><a href="http://cssgridgarden.com/">Grid Garden</a></li>
  <li><a href="https://css-tricks.com/snippets/css/complete-guide-grid/">A Complete Guide to Grid</a></li>
  <li><a href="https://gridbyexample.com/">Grid by Example</a></li>
  <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout">MDN: CSS Grid Layout</a></li>
  <li><a href="https://www.youtube.com/watch?v=tFKrK4eAiUQ/">📺 Incredibly Easy Layouts with CSS Grid</a></li>
</ul>

<p><a href="https://codepen.io/oknoway/pen/rNVYWNK?editors=1100">Bonus Demo: CSS Grid Template Areas</a></p>

<aside class="notes">
(Nate)
Grid Layout is an extremely powerful layout model that can layout entire page areas, or small user interface elements.
The grid is an intersecting set of horizontal and vertical lines that allows you to define fixed or flexible tracks and easily place and position elements.
In this demo, we're using properties like "grid-column", "grid-row" and "grid-area" to have precision control over our layout.
Our layout is really coming together; we should start thinking about how our app will look on a smart phone.
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

<h2><a href="https://codepen.io/oknoway/pen/RwPjoaP?editors=1100">Media Queries and Responsive Design</a></h2>

<ul>
  <li><a href="http://mediaqueri.es/">Responsive design gallery</a></li>
  <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries">MDN: Media Queries</a></li>
  <li><a href="https://css-tricks.com/snippets/css/media-queries-for-standard-devices/">Media Queries for Standard Devices</a></li>
  <li><a href="http://learnlayout.com/media-queries.html">Learn CSS Layout: media queries</a></li>
</ul>

<aside class="notes">
(Nate)
Responsive design means your layout "responds" to a variety of devices or screen sizes.
We'll use special CSS syntax called "media queries" to apply different CSS rules to different conditions.
For example, a use could be using "dark mode" on their laptop, and your design could use a darker background color to match.
Most frequently, we adapt our design to the size of the user's viewport. Let's take a look at this demo…
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

<h2><a href="https://codepen.io/oknoway/pen/vYOWyyO?editors=1100">Typography and Color</a></h2>

<ul>
  <li><a href="https://www.google.com/fonts">Google Fonts</a></li>
  <li><a href="http://femmebot.github.io/google-type/">Google Web Fonts Typographic Project</a></li>
  <li><a href="http://fontpair.co/">Font Pair</a></li>
  <li><a href="http://type-scale.com/">TypeScale</a></li>
</ul>
<ul>
  <li><a href="https://flatuicolors.com/">Flat UI Colors</a></li>
  <li><a href="https://color.adobe.com/create/color-wheel/">Adobe Color Wheel</a></li>
  <li><a href="http://www.colourlovers.com/palettes">Color Lovers</a></li>
</ul>

<aside class="notes">
(Nate)
Well, our apps almost done… but before we send our prototype over to the JavaScripters for some logic, let's give it a fresh coat of paint.
We'll load up some snazzy fonts from Google Fonts, and we'll use Type Scale to generate a hierarchy for all our type.
Let's also swing by the Adobe Color Wheel and create a new color scheme to really tie it all together.
Ok, Allison, our app is all ready for you to add some JavaScript!
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

## Allison Davis (3)

---

<!-- .slide: data-background="./img/2020/devsummit/bg-4.png" -->

## JavaScript

<aside class="notes">
(Allison)

</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

### Where does JavaScript go?

- Inside a `<script>` tag.
  ```html
  <script>
    /* Put JS here*/
  </script>
  ```
- Inside a `.js` file.
  ```html
  <script src="app.js"></script>
  ```
- In your browser's [DevTools console](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_are_browser_developer_tools)
  - Right click > `Inspect Element` > `Console` tab
  - Keyboard: `Cmd+Option+I`(Mac), `Ctrl+Shift+I`(Windows, Linux)

<aside class="notes" data-markdown>
(Allison)
* What's a devtools console? we can open one up right in our web browser
* Note - keyboard shortcuts differ slightly from browser to browser
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

### [Variables](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var), [arithmetic](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators), [comparison](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators) & [logic](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators)

```js
const dogName = "Bunsen";
var year = 2020;
let skyBlue = true;

year++; // 2021
year--; // 2019

"high" + "five"; // 'highfive'

// logical 'and'
true && skyBlue; // true
// 'or'
true || false; // true
// 'not'
!skyBlue; // false
```

- [MDN's First Steps JavaScript guide](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps)
- [Try it in CodePen](https://codepen.io/araedavis/pen/qBdxKbY)

<aside class="notes" data-markdown>
(Allison)
Demo in CodePen/console

- variables can be declared with const (for unchanging values), var or let keywords
- JavaScript infers the types
- strings go in double or single quotes, numbers and booleans (true/false) do not

- we can do math
- Important, if we use an operator on a variable, it does not change the variable's value
- increment or decrement a value with double plus/double minus

- we can concatenate strings

- comparison operators

- logical operators

- Play around for yourself in CodePen or directly in your browser's console
  </aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

## [functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)

```js
function dogYears(age) {
  return age * 7;
}

dogYears(3);
> 21
```

```js
age => {
  return age * 7;
};

age => age * 7;
// these are the same!
```

<aside class="notes" data-markdown>
(Allison)
* a function definition consists of the function keyword, the name of the function, a list of parameters, the JS statements inside the curly braces that are run when the function is involved
* the return statement specifies the value returned by the function
* Defining a function does not execute it - you have to call the function in order to perform the actions within it
* functions can be anonymous (unnamed), and can be passed as arguments to other functions
* arrow syntax is another way of declaring a function - less verbose than using the function key word

</aside>

---

## [Arrays[]](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays) and [objects{}](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)

```js
var dogs = ["Ginsburg", "Bunsen"];
dogs[0]; // 'Ginsburg'
dogs.push("Spot");
dogs.length; // 3
dogs.map(dog => dog.toUpperCase()); // ['GINSBURG', 'BUNSEN', 'SPOT']

let dog = {
  name: "Ginsburg",
  age: 4,
  ageInDogYears: function(age) {
    return age * 7;
  }
};
dog.name; // 'Ginsburg'
```

[Try it in CodePen](https://codepen.io/araedavis/pen/LYVQrxJ)

<aside class="notes" data-markdown>
(Allison)

- arrays are a way to store a list of items under a single variable name
- JavaScript arrays have lots of built in methods - some array methods mutate the original, some return a new array
- objects - a collection of related data. Properties (values) and methods(functions)
  </aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

## Patrick Arlt (4)

---

<!-- .slide: data-background="./img/2020/devsummit/bg-4.png" -->

## JavaScript Patterns

<aside class="notes" data-markdown>
(Pat)
* This section shows common patterns you will see in JS code to help you understand them better
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

### JavaScript is _Asynchronous_

- JavaScript is _single threaded_
- Runs one function in its entirety
- Then run the next function
- This is the "Event Loop"
- "Callback functions" define thing that happen _later_

[Event Loop and Callbacks Demo](https://codepen.io/patrickarlt/pen/eYNGjVJ?editors=0010)

<aside class="notes" data-markdown>
(Pat)
* Talk through demo, be quick, mention JS API, events
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

### Promises

```js
function processResponse(response) {
  return response.json();
}

function doSomethingWithUser(user) {
  console.log(user); // prints a bunch of user info
}

function anyErrors(error) {
  console.error("what have you done!", error);
}

let user = fetch("https://randomuser.me/api/")
  .then(processResponse)
  .then(doSomethingWithUser)
  .catch(anyErrors);
```

Promises represent values that will be set in the future.

i.e. _I `Promise` to be a useful value in the future._

[Demo](https://codepen.io/patrickarlt/pen/XWbeBEj?editors=0010)

<aside class="notes" data-markdown>
(Pat)
* Talk through demo, be quick, mention JS API
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

### The [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) and HTML

JavaScript can interact with your HTML. The HTML on your page is represented by the DOM (**D**ocument **O**bject **M**odel).

- Select HTML elements
- Listen for events & user interactions
- Change HTML elements

[Demo](https://stackblitz.com/edit/js-8kewfg)

<aside class="notes" data-markdown>
(Pat)
* Talk through demo, mention other selectors
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

### [JavaScript Modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)

```
import { something } from 'some-file.js';
```

The future! You will encounter this more often.

[Demo](https://stackblitz.com/edit/js-jczbky)

<aside class="notes" data-markdown>
(Pat)
* Talk through demo, JS API will be able to do this later this year
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

### AMD Modules (JS API)

```
require([
  "esri/Map",
  "esri/views/MapView",
], function (Map, MapView) {
  // Map and MapView have been loaded!
});
```

`require` is a fancy way of adding `<script>` tags to load code on demand.

[Demo](https://codepen.io/patrickarlt/pen/PoqJBrg)

<aside class="notes" data-markdown>
(Pat)
* Talk through demo, current way the JS API does things
</aside>

---

### <a href="https://jsbin.com/xuxavejuqe/edit?html,js,output">Lets finish our app</a>

~120 lines of CSS, ~30 lines of JS.

<aside class="notes" data-markdown>
(Pat)
* Talk through demo, wrap up app
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

### A more complex app

[Chaining Promises JS API Sample](https://developers.arcgis.com/javascript/latest/sample-code/sandbox/index.html?sample=chaining-promises)

<aside class="notes" data-markdown>
(Pat)
* Talk through demo
</aside>

---

## Tools & Frameworks

<aside class="notes" data-markdown>
(Pat)
* This is mostly a cautionary tale
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

## Don't jump into tools

- The JS API is MORE then enough for simple mapping apps
- Add tools when you **KNOW** you will benefit from using them
- Too many tools === Lots of complexity to manage
- Don't touch tools until you feel limited

<aside class="notes" data-markdown>
(Pat)
* Don't feel rushed to learn tools the basics apply everywhere and the JS API has enough to learn
</aside>

---

## Types of tools

- Modules - Formats for splitting up and sharing code
- Compilers - Transform code often adding extra features
- Bundlers - Combine modules and other assets
- Frameworks - Architecture and structure for large apps/teams

<aside class="notes" data-markdown>
(Pat)
* General types of tools
</aside>

---

## Examples of tools

- Modules - _JS Modules_, _AMD_, CommonJS, CSS Modules
- Compilers - Babel, TypeScript, SASS, LESS
- Bundlers - WebPack, Parcel, Rollup
- Frameworks - React, Angular, Vue, Ember, Dojo, Tailwind, Bootstrap

<aside class="notes" data-markdown>
(Pat)
* Examples of tools
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

## Node JS and NPM

- [Node JS](https://nodejs.org/en/) - Run JavaScript on a server or desktop. Build web servers, APIs and CLI tools.
- [NPM](https://www.npmjs.com/) - Package manager and distribution system for JS code. Analogous to Pip or Conda in Python.

[Learn Node JS at NodeSchool](https://nodeschool.io/)

<aside class="notes">
(Pat)
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-2.png" -->

## Development tools

- Set up your local dev environment: [Do I have a web server running?](https://gist.github.com/jgravois/5e73b56fa7756fd00b89)
- Prototype with [CodePen](https://codepen.io), [JSBin](https://jsbin.com) or [StackBlitz](https://stackblitz.com/)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Chrome Developer Tools](https://developers.google.com/web/tools/chrome-devtools/javascript/)
- [Firefox Developer Tools](https://developer.mozilla.org/en-US/docs/Tools)
- [ArcGIS JS CLI](https://github.com/Esri/arcgis-js-cli)

<aside class="notes">
(Pat)
</aside>

---

## Keep learning

- [ArcGIS Developer Tutorials](https://developers.arcgis.com/labs/?product=JavaScript&topic=any)
- [MDN: Learn web development](https://developer.mozilla.org/en-US/docs/Learn)
- [CSS Tricks Beginner Guide](https://css-tricks.com/guides/beginner/)
- [Eloquent JavaScript](http://eloquentjavascript.net/)
- [You Don't Know JS](https://github.com/getify/You-Dont-Know-JS)
- [JavaScript 30](https://javascript30.com/)
- [NodeSchool](https://nodeschool.io/)
- [Command Line Power User](https://commandlinepoweruser.com/)
- [Codecademy Bash Scripting course](https://www.codecademy.com/learn/learn-the-command-line/modules/bash-scripting)
- [Front End Handbook](https://frontendmasters.com/books/front-end-handbook/2019/)

<aside class="notes">
(Pat)
</aside>

---

<!-- .slide: data-background="./img/2020/devsummit/bg-4.png" -->

Slides at <a href="http://bit.ly/2PLJft4" style="font-family: monospace;">http://bit.ly/2PLJft4</a>

<aside class="notes">
(Pat)
</aside>
