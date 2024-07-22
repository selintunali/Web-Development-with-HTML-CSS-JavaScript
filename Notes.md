
# Introduction to App Development

**Basic client-server communication through a website:**
Browser contacts the server with the name and requests the information that makes up the website. 
The server will return:
* **HTML** : that defines the structure of the page
* **CSS** : that defines the style
* **JavaScript** : that adds interactive and dynamic content


Contents displayed on a website contains elements that are either:
* **static**: previously stored
* **dynamic**: generated each time requested by client. 

Websites can be designed either:
* **reactive (or adaptive)** : designed for a specific screen size
* **responsive** : automatically re-size

Building websites and applications is divided into 2 main areas:
* **Front-end development** : HTML, CSS, JavaScript and their frameworks, libraries and tools
* **Back-end development** : Handles logic, functionality, authentication etc. May also work with databases. 


# Front-End Programming Languages

### 1. HTML (Hypertext Markup Language)

HTML is used to create the physical structure that contains elements such as text, links, images/videos etc. using **tags (</>)**.

HTML was introduced in 1990, HTML5 was developed in 2007.

**HTML5** supports pages written in **HTML** or **XML (eXtensive Markup Language)** syntax. 

        HTML
        - not case sensitive
        - unmatched quotation marks, non-terminated or uncontained elements are allowed
        - syntax rigirous

```
<!DOCTYPE html>
<html>
        <head>
                <meta charset="utf-8">
                <title>Sample Page</title>
        </head>
        <body>
                <p>Example paragraph</p>
                <!--This is a comment-->
        </body>
</html>
```
        
        XML
        - tags must be in lower case
        - code must be well formatted
        - XML parser will stop if encounters a situation where syntax isn't well formated. 

```
<?xml version="1.0" encoding="utf-8"?>
<html xmln="https://www.w3.org/1999/xhtml">
        <head>
                <meta http-equiv="Content Type"
                content="application/xhtml+xml;charset = ISO-8859-1"/>
                <title>Example document</title>
        </head>
        <body>
                <p>Example paragraph</p>
        </body>
</html>
```
**NOTE: `<!DOCTYPE html>` is a declaration not an element**

HTML5 also defines a **sandboxed attribute** , used on `<iframe>` elements which specifies extra set of content restrictions and can be used when hosting untrusted content. (e.g.`<iframe src="https://example.com" sandbox></iframe>`)

**Must Know HTML Elements:**
- `<hr>`: adds horizontal line
- `<h1> </h1>`: Largest heading; `<h6> </h6>`: Smallest heading
- `<br>`: breaks line
- `<a href="https://..">Text</a>` : Hyperlink reference. Can also link to a section in code with #id instead of hyperlink.
- `<ul> </ul>` : unordered list
- `<ol> </ol>` : ordered list
- `<li> </li>` : list item
- `<table> </table>`
- `<tr> </tr>` : table row
- `<th> </th>` : table heading
- `<td> </td>` : table data
- `<img src= "https..." width=... height=..>`
- `<figure> </figure>` : structural element that allows content grouping
- `<figcaption> </figcaption>` : Figure caption; usually comes after img element
- Comment in HTML: `<!--This is a comment -->`
- `<div> </div>` : structural element used to group content
- `<section> </section>` : structural element used to group more specific content
- `<article> </article>` : even more specific than section element; elements are meaningful on their own without the rest of the code
- `<aside> </aside>` :  another structural element used for grouping
- `<fieldset> </fieldset` : creates a visual grouping box usually followed by `<legend>TitleOfFieldSet</legend>`
- Input Element:
  - `<input type="date">` : no time zone e.g. yyyy-mm-dd ; Chrome displays as drop-down calendar
  - `<input type="email>"` : regular text input field
  - `<input type="number>"` : accepts any number value ; can be used with min and max values e.g. `<input type="number min="5" max="7">`
  - `<input type="tel>"` : telephone number but does not enforce numeric only as different country or area codes might require special characer such as + or () ; can set a pattern e.g. `<input type="tel pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}>"`
  - `<input type="email" placeholder="abc@gmail.com">` or `<input type="email" placeholder="abc@gmail.com" required >` 
  - `<input type="range" id="rate" min="1" max="20" value="10.25" step="0.25" onchange="updateRate()"> `
  - `<input type="text" list="fruits">` <br>
        `<datalist id="fruits">`<br>
                `<option value="apples"></option>`<br>
                `<option value="bananas"></option>`<br>
                `<option value="oranges"></option>`<br>
        `</datalist>`
- `<span id="rate_val">10.25</span>%` : `<span>` tag in HTML is an inline container used to group and style a part of text
- `<textarea id="new_recommendation" cols="500" rows="10" placeholder="Message"></textarea>` : Adds a text box for large input text
- `<script src="Function.js"></script>` : used within header to call JavaScript file for dynamic functions
- `<link rel="stylesheet" href="Style.css">` : used within header to call CSS file for page style
- Inline elements for styling content directly in the HTML: 
  - `<strong> </strong>` makes text bold
  - `<u> </u>`underlines e.g. `<p><strong><u> Planets in the solar system: </u></strong> </p>`
  - `<mark> </mark>` highlights between text in yellow
- `<span>&#8220;</span>Some text<span>&#8221;</span>` adds quotation marks between text

**NOTE: Use # when calling a HTML element by it's id**

### 2. CSS (Cascading Style Sheets)

CSS adds style and flair to the page

HTML references CSS in 3 ways (see Week1 material for examples):
1) Inline CSS: within HTML e.g. `<p style = "color : red"> This is a paragraph </p>`
2) Internal CSS: within HTML ; used for a single page and increases load time! ; used with` <style>` tag within header

3) External CSS : separate css file ; styles entire website ; must use link tag in header section `<link rel = "stylesheet" href = "Style.css"> `

Can also use combination of 3 ways, the priority order is: **Inline>Internal>External**

**CSS Selectors:** patterns used to select and style HTML elements
1) **Tag Selectors:** targets HTML elements using their tag name
```
h1{
        color : white;
        font-size : 24px;
}
```
2) **ID Selectors:** targets specific element using it's unique id

```
#header {
        /*Styles element with id="header"*/
        background-color : white;
        padding: 10px;
}
```

3) **Class Selectors:** targets HTML elements with specific class attribute. 
```
.highlight {
        /*Styles for elements within class = "highlight"*/
        background-color : white;
        color : red;
}
```

**NOTE: link is a self-closing element** 

**NOTE: Not all browsers fully support all features in HTML5 or CSS3 specifications. Browse caniuse.com to search for the feature.** 

**NOTE: `<div style="clear:both;"></div>` is used to clear floats in layouts and to control document flow.**

### 3. JavaScript

JavaScript is an object-oriented programming language used in conjunction with HTML and CSS to add interactivity to a website. 

*To give an example, use HTML to add a login button, CSS to style that button, and JavaScript to add login functionality.*

Scripting (`<script>`) can be included directly inside HTML for short scripts or src attribute is used to point to an external javascript file e.g. `<script src="script.js"></script>`

Scripts are bound to events so they can run automatically for interactivity. Examples of **event binders**: *onload=, onclick=, onmousehover=, onselect=, onsubmit= , onchange= etc.*

*Code Example:*
```
<button type = "button" onclick="showAnswers()">Show Solution
        <script>
                function showAnswers() {
                        alert("A")
                }
        </script>
</button>
```

**NOTE: scripting may not be allowed by every browser, the `<noscript>` tag provides an alternate when scripting is disabled.**


2 data types of JavaScript:

**1. JavaScript Primitives:** (immutable)
- **string** ("Hello")
- **number** (42, 3.14)
- **boolean** (true or false)
- **null**
- **undefined**

**2. Wrapper Objects:** (mutable; provide way to treat primitives as objects)
- new **String**("hello")
- new **Number**(42)
- new **Boolean**(true)
- numArray = new **Array**(0,1,2,3,4,5)
- var newDate = new **Date**("2012-1-17 13:15:30"); var newDate = new Date(2012,0,17); var newDate = new Date(); new Date().getFullYear() 
- throw new **Error**("Only values 1-10 are allowed") : custom error message

**NOTE: Month number starts from zero!**

**NOTE: If no date is provided means current local time**

**NOTE: getFullYear() in JavaScript will retrieve year from date**

**NOTE: Can parse number to int or float: parseInt(principal) + parseFloat(interest)**

Example:
```
var a = new String(“Hello”); // String Object
var b = “Hello”; // Primitive String
a===b; //false ;  checks type and value
```

**Creating Objects:**
1) **Object Literals:** most common way to create objects
```
let person = {
    name: "Jason",
    age: 20
};

console.log(person); // { name: 'Jason', age: 20 }
```

2) **Constructor Functions:** 

'this' refers to the current instance of the object. 

```
function Person(name, age) {
    this.name = name;
    this.age = age;
}

let person1 = new Person("Jason", 20);
console.log(person1); // Person { name: 'Jason', age: 20 }
```

3) **Class Syntax** introduced with ES6
```
class Rectangle {
    constructor(height, width){
        this.height = height;
        this.width = width;
    }
}

let myRectangle = new Rectangle(10, 5);
console.log(myRectangle); // Rectangle { height: 10, width: 5 }
```

4) **`Object.create()` & Prototype:**
```
let personPrototype = {
    greet: function() {
        console.log("Hello, my name is " + this.name);
    }
};

let person = Object.create(personPrototype);
person.name = "Jason";
person.age = 20;

console.log(person); // { name: 'Jason', age: 20 }
person.greet(); // Hello, my name is Jason
```

New function or property can be added to an object by modifying the prototype of the object. For instance: 

```
Person.prototype.lastname = "Smith";
Person.prototype.fullName = function() {
        console.log(this.name + " " +this.lastname);
}
```

**NOTE: typeof prints type `e.g. typeof new String("abc") // returns object`**

**NOTE: .valueOf or .toString converts object to primitive `e.g. typeof (new String("abc")).valueOf //returns string`**

**JavaScript Functions:**
A function is a block of code which can be called from any point in the script.

Functions take arguments and return results. 

If there is no specific return type is declared, then the function returns whatever type is required.

For example:

```
functions add(x,y){
        return x+y;
}
var x = add(1,2); //returns 3
var add("hello", "world"); //returns helloworld
```
another example: 

```
var total = add(10,"3"); // returns "10 3"
```
**Self executing functions** start running immeadiately after they have been declared and can be anonymous.

```
(function () {
        //statements
})
```
**Arrow functions syntax**
```
let functions=(x,y)=> {
         return x+y;
}
```
or if a single value
```
let functions=(x,y)=> x+y;
```


**JavaScript Operators:**

1) **Arithmetic Operators:** +, -, *, /, **, %, +=, -=, etc.
2) **Comparison Operators:** ==, === checks if values are equal and of the same type, !=, <, >, <=, >=, etc.
3) **Logical Operators:** && and, || or, ! if condition is not met

**Collections:**
1) **Array:** is an indexed collection. The index starts from 0.
```
let myArray = ["Jack", "Jill", 4, 5 , true]
console.log(myArray[0]) // returns Jack
console.log(myArray[4]) // returns true
```
To iterate through arrays there is a special type of loop **forEach**
```
let myArray = ["Jack","Jill",4,5,true]
myArray.forEach(element => {
    console.log(element)
})
```
2) **Map:** object maps a key to a value
```
let myMap = new Map();
//Add a key-value pair to the map, with a key of "name" and a value of "John". 
myMap.set("name", "John")
//Add another key-value pair to the map, with a key of "age" and a value of 22.
myMap.set("age", 22)
myMap.forEach((val,key) => {
    console.log(key, " - ", val)
})
``` 

**JavaScript Has 6 Types of Errors:**
- **EvalError:** An error related to the eval() function
- **RangeError:** Thrown when a value is outside the allowable range.
- **ReferenceError**: When a non-existent variable is referenced.
- **SyntaxError:** When there is a syntax mistake in the code.
- **TypeError:** When a variable or parameter is not of a valid type.
- **URIError:** When there is an error in encodeURI() or decodeURI().

**Expert Recommendations:**
- Avoid global variables to avoid name collision
- switch-case statements are useful to replace multiple if-else conditions
```
user_input = parseInt(user_input)
    switch(user_input){
        case 1: console.log("Sunday"); break;
        case 2: console.log("Monday"); break;
        case 3: console.log("Tuesday"); break;
        case 4: console.log("Wednesday"); break;
        case 5: console.log("Thursday"); break;
        case 6: console.log("Friday"); break;
        case 7: console.log("Saturday"); break;
        default: console.log("Invalid entry");
    }
```
- loops are useful when same block of code need to be executed many times
```
for (let i=0; i<10; i++) {
        console.log(user_input, " X ", i, " = ", user_input*i)
    }
```

# DOM (Document Object Model)

DOM is the programming interface between HTML or XHTML and JavaScript. It allows JavaScript to access and modify the content, structure, and style of web pages.

**Basic DOM Model for browsers:** (top to bottom)

![Alt text](<Screenshot 2024-06-14 at 4.29.45 PM.png>)

- **Window Object** : controls the environment; automatically created when browser loads the page. *Window object dialog boxes: window.alert (code: alert("message);), window.confirm (code: confirm("message");), window.prompt (code: prompt("message", "defaultReply"))*

- **History Object** : keeps internal details about recent history on the browser
- **Location** : contains information about URL
- **Navigator Object**
- **Screen Object** : useful for determining screen size of the browser
- **Document Object** : provides access to all HTML elements on a page


**A DOM tree** is an in-memory representation of a document. HTML user agents aka browsers parse markup into a DOM tree. 

The object diagram can also be represented as a tree structure that corresponds to the structure of the HTML document.

![Alt text](<Screenshot 2024-06-14 at 4.40.41 PM.png>)


The branches of the tree structure are termed **nodes**. There are two types of nodes in W3C DOM: 

1) **Element Nodes:** All HTML tags (html, head, meta, title ,body etc.)
2) **Text Nodes:** actual text that go between an element start tag and end tag *e.g. `<title>Page Title</title>`*


# DOM Tree Accessors

DOM Tree Accessors are HTML document APIs that provide access to all HMTL elements on a page. Used in JavaScript.

- **document.getElementById('id')**
- **document.getElementsByTagName(tagName**) : returns an array of elements with the tagName
- **document.createElement('tagName' )** : use it with **insertBefore**, **appendChild** or **replaceChild**
```
<head>
        <script>
                function addPara() {
                        var newPara = document.createElement('p');
                        var newText = document.createTextNode("Hello, World!");
                        newPara.appendChild(newText); //appends new text to paragraph
                        document.body.appendChild(newPara); //paragraph is appended to body
                }
        </script>
</head>
<body onload="addPara()">
</body>
```
- **element.innerHTML** : retrieves or sets the contents within an HTML
- **element.style.propertyName = value** : retrieves or sets the inline CSS style for a particular element e.g. `element.style.color="blue`
```
< div id = "div1" style="color: blue">
</div>
<script>
        var div1 = document.getElementById("div1");
        div1.style.color = "red";
</script>
```

**NOTE: This will overwrite inline CSS**

- **element.setAttribute(attrName, attrValue**) e.g. `document.getElementById("theImage").setAttribute("src", "another.gif");`
- **element.value.trim() != ""** : removes whitespaces
- **element.focus()** : useful to return focus to input box after an alert box condition such as if entered value is not allowed. 

An alternative way to access nested objects  is the dot notation 

Ex: element field1 can be accessed by: 
- document.forms[0].elements[0] or
- document.forms["form1"].elements["field1"] or
- document.form1.field1

![Alt text](<Screenshot 2024-06-14 at 4.56.49 PM.png>)

# APIs (Application Programming Interface)

API is a way two applications communicate with each other

### REST (Representational State Transfer) APIs

REST APIs follow the CRUD (Create, Read, Update and Delete) paradigm. These CRUD operations have aliases as follows:

- Create -> POST
- Read -> GET
- Update -> PUT
- Delete -> DELETE


# Frameworks

A framework provides a skeleton for the application, dictating it's structure and flow. 

        Libraries
        - collection of re-usable code
        - code (from library) is called when desired
        - can solve specific problem or feature
        - ex: JQuery is a JavaScript library that                                 
        simplifies DOM manipulation

        VS

        Framework
        - acts as a skeleton
        - should be determined and used from start
        - Framework calls the code
        - Defines workflow you must follow
        - ex: Django for Python web development


### JavaScript Front-End Frameworks

- **React** (developed by Meta) : focuses on building user interfaces and often used for single-page appliations where content updates frequently

- **Angular** (developed by Google) : comprehensive solution for developing highly interactive web applications with strong emphasis on reusable components and modules. 

- **Vue** (maintained by community) : It's main focus is the view layer which includes UI, buttons, visual compoents. It's flexible and scalable, integrates well with other frameworks. Very adaptable therefore can be used as a library or framework

### Node.js

Node.js is not a framework but a **runtime** that allows JavaScript to be used for server-side development, enabling full-stack development with JavaScript.

# Top rated front-end frameworks

1. React
2. Node.js
3. jQuery
4. Angular
5. Express

# React

Open source JavaScript library developed by Meta. 

**Features of React:**
- **Component based architecture** : e.g. Header, Left Section, Right Section, Footers. Encapsulating UI functionality in individual files eliminates code duplication and emphasizes reusable UI elements

- **Declarative syntax** : this lets developers focus on intended UI behaviour while React manages the underliyng DOM (focuses on what to do rather than how)

- **Virtual DOM** : Generates virtual copies when changes occur in any component and compares them to real DOM updating only the essential segments to optimize performance and minimize DOM modifications

- **1-way data binding** : ensures data flows unidirectionally form parent to child components simplifying data management and reducing bugs

- **JavaScript XML (JSX)** : JSX is a JavaScript extension that enables HTML-like code within JavaScript

- **Hook Employment** : Hooks allow developers to handle states and other React features eliminating the need for class-based coding. 

**React folder structure:**
- **Node_modules:** contains all dependencies
- **public:** contains static assets like HTML files, images and fonts
- **src:** contains source code for application. Inside src, there will be:
   - **App.css**
   - **App.jsx:** Root component of the application
   - **index.css**
   - **index.html:** Entry point for web app
   - **main.jsx:** Entry point for the application
   - **package.json:** Contains metadata about the project and dependencies. Also includes scripts for running, building and testing application. 
   - **vite.config.js:** Configuration settings for Vite build tool
   - **.gitignore**
   - **README.md**

# Build Tools:
1) **CRA Tool: npx create-react-app app-name**
- installs unnecessary files and folder
- leads to large file size

2) **Vite Tool: npm create vite@latest**
- improved development tool
- Used with **React**, **Angular** or **JavaScript**

**How to create React project using Vite Tool:**
1) Type npm create vite@latest
2) Select React as framework
3) Select JavaScript as variant
4) Terminal will give instructions
5) Link and port number will be displayed
6) command: npm run dev

# EcmaScript6 (ES6, 2015)

New features were introduced in JavaScript as part of ES6 are:

**1. Keyword: var**
It has global scope

**2. Keyword: let**
It has local scope
*e.g.*
```
{
        let num = 5;
        console.log(num); //returns 5
        num = 6;
        console.log(num); //returns 6
}
console.log(num); //Error: num out of scope
```

**3. Keyword: const**
It cannot change
*e.g.*
```
const num = 5;
console.log(num);
num = 6; //Error
```

**4. Arrow Functions with parameters**

**If returns a value must use curly brackets!**
*e.g.*
```
const oneParamArrowFunc = name => {return "hello" + name };
```

*e.g.*
```
const twoParamsArrowFuncWithoutReturn = (first, last) => console.log("hello" + first + " " + last);
```

*e.g.*
```
cons twoParamsTwoLinesArrowFunc = (first, last) => { const greeting = "hello" ; return greeting + " " + first + " " + last;}
```

**5. Promise**

A promise is an object which represents the completion of an asynchronous operation and it's return value. Takes states: pending, fulfilled or rejected. 

```
let promiseArgument = (resolve, reject) => {
        setTimeout(()=> {
                let currTime = new Date().getTime();
                if(currTime % 2 === 0){
                        resolve("Success!")
                  else{ reject("Failed!!!) }
                }
        }, 2000)};

let myPromise = new Promise(promiseArgument); // function setTimeout passed to constructor of the promise object 
```

**6. Classes**
Makes OOP feasible
Blueprint for creating objects

*e.g.*
```
function Person(name, age) {
    this.name = name;
    this.age = age;
}
let person1 = new Person("Jason", 20);
console.log(person1);
console.log(person1.name);
console.log(person1.age);

```

Use **constructor** when want to create an object of class. New object of that class can be created using the "new" keyword.

*e.g.*
```
class Rectangle {
        constructor(height, width){
                this.height = height;
                this.width = width;
                console.log("Rectangle Created");
                console.log("Height" + this.height);
                console.log("Width" + this.width);
        }
};
let myRetangle = new Rectangle(10,5)
```

**Inheritance**
The subclass may call the superclass constructor with a **super()** method call

*e.g.*
```
class Square extends Rectangle
{
        constructor(height, width){
                if(height===width){
                        super(height, width)
                }else{
                        super(height, width);
                }
        }
}
let mySquare =  new Square(5,5)
```

# Introduction to JSX (JavaScript Syntax Extension / JavaScript HTML)

Use JSX to create React elements which then renders elements to DOM. 
*e.g.*
```
const myHeader = <h1>This is a sample JSX code snippet</h1>
```

Browsers don't understand JSX, so need **Babel** to compile JSX code and transform it into standard JavaScript objects. 

Use command '**create-react-app**' to handle the compilation. 

**!JSX outperforms JavaScript because it optimizes during compilation and it more secure!**

# Packages and Package Managers

**A package** contains app files, instructions for installation and metadata.

**Package managers** take care of finding, installing, maintaining and unistalling packages. To name a few, pip and conda are python package managers

# Build Automation

Build automation does the following:
- downloads dependencies
- compiles source code to binary code (C#/F#/VS -> CIL ("Common Interpreted Language" aka the language of .NET))
- packages binary code
- runs tests and deploys to production systems

# Languages and Tools Working with Databases

- SQL
- Object Relational Mapping (ORM) e.g. Dapper in C#, SQLAlchemy in Python

# VS Code extensions
- C# Development Kit
- Live Server

# Instruction to run a full web app
- Right click on html and select 'open with live server'