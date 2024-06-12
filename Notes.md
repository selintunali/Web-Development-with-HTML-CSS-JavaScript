
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
                <p>Example paragrapg</p>
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
- `<figcaption> </figcaption>` : Figure caption; usually comes after img element
- `<figure> </figure>` : structural element that allows content grouping
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
  - `<input type="text" list="fruits">` <br>
  `<datalist id="fruits">`<br>
        `<option value="apples"></option>`<br>
        `<option value="bananas"></option>`<br>
        `<option value="oranges"></option>`<br>
 `</datalist>`
- `<script src="Function.js"></script>` : used within header to call JavaScript file for dynamic functions
- `<link rel="stylesheet" href="Style.css">` : used within header to call CSS file for page style
- Inline elements for styling content directly in the HTML: 
  - `<strong>` makes text bold
  - `<u>`underlines e.g. `<p><strong><u> Planets in the solar system: </u></strong> </p>`

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

**NOTE: Not all browsers fully support all features in HTML5 or CSS3 specifications. Browse caniuser.com to search for the feature.** 

**NOTE: `<div style="clear:both;"></div>` is used to clear floats in layouts and to control document flow.**

### 3. JavaScript

JavaScript is an object-oriented programming language used in conjunction with HTML and CSS to add interactivity to a website. 

*To give an example, use HTML to add a login button, CSS to style that button, and JavaScript to add login functionality.*

Scripting (`<script>`) can be included directly inside HTML for short scripts or src attribute is used to point to an external javascript file e.g. `<script src="script.js"></script>`

Scripts are bound to events so they can run automatically for interactivity.
*Examples of scripts that are tied to instrinsic events: onload=, onclick=, onmousehowver=, onselect=, onsubmit= etc.*

*Code Example:*
```
<button type = "button" onclick="showAnswers()">Show Solution
        <script>
                function showAnswers() {
                        altert("A")
                }
        </script>
</button>
```

NOTE: scripting may not be allowed by every browser, the `<noscript>` tag provides an alternate when scripting is disabled. 

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
- var newDate = new **Date**("2012-1-17 13:15:30"); var newDate = new Date(2012,0,17); var newDate = new Date();
- throw new **Error**("Only values 1-10 are allowed") : custom error message

**NOTE: Month number starts from zero!**

**NOTE: If no date is provided means current local time**

**Creating Objects:**
1) **Object Literals:** most common way to create objects
```
let person = {
        name: "John",
        age: 30,
        isStudent: false,
        greet: function() {
                console.log("Hello, " + this.name);
        }
};
```

2) **Constructor Functions:** 

'this' refers to the current instance of the object. 

```
function Person(name, age) {
        this.name = name;
        this.age = age;
        this.greet = function() {
                console.log("Hello, " + this.name);
        };
}

var p = new Person("John", 30);
alert(p.greet()); // displays Hello, John
```

3) **`Object.create()` & Prototype:**
```
let proto = {
        greet: function() {
                console.log("Hello!");
        }
};

let person = Object.create(proto);
person.name = "Bob";
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

**Self executing functions** start running immeadiately after they have been declared and can be anonymous.

```
(function () {
        //statements
})
```

**Expert Recommendations:**
- Avoid global variables to avoid name collision

# DOM (Document Object Model) Tree

A DOM tree is an in-memory representation of a document. It describes how a website is structured.

HTML user agents aka browsers parse markup into a DOM tree. 

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

# APIs (Application Programming Interface)

API is a way two applications communicate with each other

### REST (Representational State Transfer) APIs

REST APIs follow the CRUD (Create, Read, Update and Delete) paradigm. These CRUD operations have aliases as follows:

- Create -> POST
- Read -> GET
- Update -> PUT
- Delete -> DELETE


# Frameworks

A framework provide a skeleton for the application, dictating it's structure and flow. 

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


### JavaScript Frameworks

- **React** (developed by Facebook) : focuses on building user interfaces and often used for single-page appliations where content updates frequently

- **Angular** (developed by Google) : comprehensive solution for developing highly interactive web applications with strong emphasis on reusable components and modules. 

- **Vue** (maintained by community) : It's main focus is the view layer which includes UI, buttons, visual compoents. It's flexible and scalable, integrates well with other frameworks. Very adaptable therefore can be used as a library or framework

### Node.js

Node.js is not a framework but a **runtime** that allows JavaScript to be used for server-side development, enabling full-stack development with JavaScript.

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