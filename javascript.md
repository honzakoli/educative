# Javascript notes

## Introduction and fundamentals of javascript

- syntax simmilar with C and PHP
- Object in javascript is like an associative array in PHP
- instead of using "->" javascript uses "."
- javascript uses dynamic types of variables
- best javascript documentation -> MDN

⋅⋅* including javascript into the page
- javascript code/link to a code on a HTML page is between the **script** tags
- its better to put the script into the **body** element - it works better

### Similarities with C or PHP
- semicolons
- variables
- operators

### Javascript Output
- Writing into an HTML element, using innerHTML.
- Writing into the HTML output using document.write(). **THIS ONLY FOR TESTING!**
- Writing into an alert box, using window.alert().
- Writing into the browser console, using console.log().

### Some javascript (syntax) rules
- defining a variable: **var** name = "value";
- connecting two strings: "string1" + " " + "string2";
- var z = x ** 2; -> same as pow(x,2)
- arrays in javascript are zero-based -> index for a first item is 0
- null value is considered as empty object -> null === undefined false, null == undefined true
- using js function without () returns the definition instead of the return value

### Objects

- In Javascript, objects are basically associative arrays
- inheritance of the objects in javascript is basically a linked-list system
- basic object declaration
```
var object {
	property: value,
	method: function(){};
}
```
- unable to create instances

-object with a constructor
```
function Car(znacka, barva){
		this.label = znacka;
		this.color = barva;
		this.method = function(){
			...
		};
	}
```
- able to create instances -> new auto = car(skoda, cervena);

### Javascript methods

#### getElementBy

- interacts with elements on a HTML page
- .document.getElementById -> .document says work with the elements on a page
- getElementBy**Id/ClassName**="something" -> work with id/class called "something"
⋅⋅* Changeable content - this is usually at the end of the method
* .innerHTML -> changes the content of elements like paragraph or heading
* .src -> changes the source (for example image)
* .style.**styleName="value"** -> changes the style of an element
* .style.display="**none/block**" -> hide/show an element

#### String methods
- length of a string
```
var txt = "text";
var sln = txt.length;
```
- indexOf() -> find a specific text in a string, return the first index of it
- lastIndexOf()->same as indexOf but return the last index of it, also searches from the last index
- search() -> simmilar to indexOf() but with some differences
- slice() -> extracts a part of a string and returns the extracted part in a **new string**
- substr() -> same as slice but the second parameter is a lenght of the extracted string. if there is no second parameter, it returns all from the first parameter
- replace() -> replaces specific part with another, return **new string**
- toUpperCase() -> changes the string to upper case
- toLowerCase() -> changes the string to lower case
- concat() -> joins two or more strings, same as "+"
- trim() -> removes whitespace from both sides of a string
- str[i] -> returns a specific character on **i**-th index
- split() ->converts string into an array

#### Number methods
- return a number as a string
```
x = 5
y = x.toString();
```
- toExponential() -> returns a string, with a number rounded and written using exponential notation -> 9.66e+0
-toFixed() -> returns a string with a rounded number - 9.654 -> 9.7
-toPrecision90 -> same as toFixed, but can return longer string - 9.65 -> 9.65000
- Number() -> convert variable into a number; properties -> MIN/MAX_VALUE, POSITIVE/NEGATIVE_INFINITY, NaN; **cannot be used on vars** -> variable.MIN_VALUE is wrong
- parseInt()/parseFloat() -> parse a string into a int/float
- when you put something else into a number method it usually returns NaN

#### Array methods
- convert array to string
```
var fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.toString();
```
- join() -> same as toString, but the separator can be specified
- pop() -> remove the last item of the array which is also a return value
- push() -> add a new item at the end of an array and returns the lenght of the pushed array
- shift() -> remove the first item of the array which is also a return value, shifts the remaining items to lower index
- unshift -> add a new item at the beggining of an array and shifts the others to higher index
- concat(), slice() -> same usage as with strings

#### toString()
- converts the argument(s) into a string separated by a comma
- All JavaScript objects have a toString() method

#### Math.random()
- returns a random number lower than 1
- proper random function
```
 Math.floor(Math.random() * 10);
```

- if you want to set the min and max value
```
function getRndInteger(min, max) {
  return Math.floor(Math.random() * (max - min + 1) ) + min;
}
```

### javascript data types
- number
- string
- boolean
- undefined
- object (arrays are also considered as an object)
- **typeof()** -> returns the type of a variable
- Number() -> converts string to a number
- String() -> converts number to a string

### Events
- javascript reactions on HTML events
- HTML events -> page loading finished, input field changed, button clicked
- common javascript events: onclick, onmouseover, onmouseout, onkeydown, onload
- full list of javascript events: https://www.w3schools.com/jsref/dom_obj_event.asp
- syntax:
```
<element event="some JavaScript">

// + example

<button onclick="this.innerHTML = Date()">The time is?</button>

// better way:

<button onclick="displayDate()">The time is?</button>

// ... and the script of displayDate is somewhere else
```

### Regular expressions
- powerfull search tool
- syntax -> /pattern/modifiers;
⋅⋅* useful modifiers
* i -> case-insensitive matching
* g -> global match (not only the first match)
* m -> multiline matching
-regExp modifiers reference: https://www.w3schools.com/js/js_regexp.asp
- test() -> returns true or false depending od the result of the search
- exec() -> returns the searched value if it finds what is needed

### Error handling
- try, catch, throw, finally
- full error handling reference https://www.w3schools.com/js/js_errors.asp


### Variables and functions
- variables declared inside a functions cannot be used outside of a function **unless** the value is assigned without a declaration of the function
- const variables can be declared but cannot be changed
- global scope -> the whole window object
- you can use variable/function before it has been declared/defined
- strict mode forbids to use undeclared/undefined variables/functions
- adding strict mode
```
"use strict";
```
⋅⋅* Let and Var keyword
- outside block are both global, but let is not accesible via *window* object
- var declared inside the block is accessible throughout the block, even if it is declared inside the loop - it is something like opposite inheritance of the variable
- let declared inside the block is not accessible throughout the block - there is not opposite variable inheritance

### Reserved Words
- full reference: https://www.w3schools.com/js/js_reserved.asp
==============================================================================

### Advanced

### HTML DOM
- **DOM = DOCUMENT OBJECT MODEL**
⋅⋅* each page has HTML DOM methods and properties
* **methods** - actions that can be performed on HTML Elements(getElementById)
* **properties** - values of HTML elements that can be set or changed(innerHTML)

#### Document Object
- document object represents the whole web page and all elements can be accessed vith this object
⋅⋅* functions
- finding HTML elements -> getElementById
- changing HTML elements -> innerHTML
- adding/deleting elements -> document.createElement(*element*)

#### Elements
- HTML elements
⋅⋅* can be found by:
* id
* tag name
* class name
* css selectors
* HTML object collections

#### HTML and CSS
- Javascript can change HTML and CSS content

#### Animations
- simple animation code demonstration
```
<div id ="container">
  <div id ="animate">My animation will go here</div>
</div>
```
- div (container) should be position relative
- div (animate) should be position absolute

simple javascript code for animation
```
function myMove() {
  var elem = document.getElementById("animate");
  var pos = 0;
  var id = setInterval(frame, 5);
  function frame() {
    if (pos == 350) {
      clearInterval(id);
    } else {
      pos++;
      elem.style.top = pos + 'px';
      elem.style.left = pos + 'px';
    }
  }
}
```
* and the running button -> ```<p><button onclick="myMove()">Click Me</button></p>```

#### Events
- content of the events above
- syntax: *onclick=JavaScript*
⋅⋅* Typical events
- onmouseover
- onclick
- onload

##### Event Listener
- syntax -> *element.addEventListener(event, function, useCapture);*
- do not use *"on"* prefix in the event listener
⋅⋅* simmilar as normal events, but:
* you can add many events to the same element without overwriting the existing ones
* you can add events of different types to the same element

- *removeEventListener()* method removes event handlers that have been attached with the addEvenetListener() method

#### Navigation
- HTML page has a node structure -> html is the parent of them all, body is his first child etc
- there are several "pointers" that refers to specific element using family relations ((sibling, parent, child) of the element)
- full reference here: https://www.w3schools.com/js/js_htmldom_navigation.asp
- also node reference: https://www.w3schools.com/js/js_htmldom_nodes.asp
- there is also something like **NodeList** -> a list of nodes extracted from a document (object)

### BOM
- **BOM = BROWSER OBJECT MODEL**

#### Window
- representing the browser window
- global variables are properties of this object
- some methods -> *window.open(), window.close(), window.moveTo(), window.resizeTo()*

##### Screen
- *window.screen* object contains information about the user screen
- can be written without the window prefix

##### Location
- *window.location* can be used to get the current page address (URL) and to redirect the browser to a new page
- can be written without the window prefix

##### History
- *window.history* object contains the browsers history
- can be written without the window prefix
⋅⋅* Some methods:
* history.back() - same as clicking back in the browser
* history.forward() - same as clicking forward in the browser

##### Navigator
- information of user's browser
- useful for getting information if the cookies are enabled

##### Popup Alert
⋅⋅* there are three kind of popup boxes
* Alert box -> used if you want to make sure information comes through to the user
* Confirm box -> used if you want the user to verify or accept something.
* Prompt box -> used if you want the user to input a value before entering a page

- syntax -> *window/confirm/prompt.alert("sometext");*
- can be written without the *window* prefix -> *alert("sometext");*

##### Timing Events
- window object allows execution of code at specified time intervals -> timing events
- can be written without the window prefix
⋅⋅* Two main methods:
* *setTimeout(function, milliseconds)* -> Executes a function, after waiting a specified number of milliseconds
* *setInterval(function, milliseconds)*- > Same as setTimeout(), but repeats the execution of the function continuously
⋅⋅* functions that stops timeout and interval
* clearTimeout(timeoutVariable) -> timeoutVariable is variable where the function is stored
* clearInterval(timerVariable) -> timerVariable is variable where the function is stored

#### Cookies
- Cookies remember the information about the user (something like a small database with basic information list about the user)
- in javascript, cookies are *document* object property -> *document.cookie*
- example of a cookie create or edit -> *document.cookie = "username=John Doe";*
- javascript can be read like this -> *var x = document.cookie;*
- delete cookie is easy, you just change the 'expires' value to a passed date
⋅⋅* Javascript Cookie Example
* A function to set a cookie value
	```
	function setCookie(cname, cvalue, exdays) {
  var d = new Date();
  d.setTime(d.getTime() + (exdays*24*60*60*1000));
  var expires = "expires="+ d.toUTCString();
  document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
}
	```
* A function to get a cookie value
```
function getCookie(cname) {
  var name = cname + "=";
  var decodedCookie = decodeURIComponent(document.cookie);
  var ca = decodedCookie.split(';');
  for(var i = 0; i <ca.length; i++) {
    var c = ca[i];
    while (c.charAt(0) == ' ') {
      c = c.substring(1);
    }
    if (c.indexOf(name) == 0) {
      return c.substring(name.length, c.length);
    }
  }
  return "";
}
```
* A function to Check a Cookies
```
function checkCookie() {
  var username = getCookie("username");
  if (username != "") {
   alert("Welcome again " + username);
  } else {
    username = prompt("Please enter your name:", "");
    if (username != "" && username != null) {
      setCookie("username", username, 365);
    }
  }
}
```
- put it alltogether and try!

### Useful tips
- always use **console.log()** for debugging
- undefined is not null
⋅⋅* always declare variables on top of the script and initialize them immidiately, even inside a function
* string -> var str = "";
* number -> var num = 0;
- never declare any date type as an object (new array(), new number()...)
- use === comparsion
- never use eval()
- avoid global variables

- when declaring a variable and you put a number in quotes, the rest of the numbers will be treated as strings, and concatenated. This is same with string + number, but the string has to be declared first (on the left side)



