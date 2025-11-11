---
lastSync: Wed Feb 12 2025 11:15:46 GMT-0500 (Eastern Standard Time)
created: 2025-01-08T10:41:51-05:00
tags:
  - school
---
# COMP 125-004 (Client-Side Web Development)
**Class 1 (1/8/2025)**
Intro/Course Outline
6 Assignments (10% each, 60% total)
2 Tests (20% each, 40% total, last test is fully MC; 100 Questions)(Week 6 and Week 14)

History of JavaScript and other scripting languages

Scripting language is read line-by-line by a interpreter
Programming language is compiled by a compiler.

DOM (Document Object Model): how to access contents of a web page and user actions within that page
BOM (Browser Object Model)

Two tier system (client and server)
3 tier (client, server, database)

JavaScript and server-script operate in different environments

<script></script> browser stops loading web page and uses script when it encounters this

Property: 
Method: pass arguments

JavaScript case sensitivity: all object names must be lowercase.
Rules for variable names/ identifiers
- can start with uppercase, lowercase, ASCII, dollar sign or underscore
- can have numbers but not as first character
- no spaces
- cannot be a reserved word/keyword

**Class 2 (1/9/2025)**
*Event:* a specific circumstance monitored by JavaScript, that your script can respond to in some way.
Can include mouse (mouseover), keyboard and touchscreen. Cna also detect changes (change {when an element such as a text box changes})

*Event handler:* code that is executed in response to a specific event occurring on a specific element.

async and defer keywords: 
- Default behaviour is for JS file to load when script element is encountered in HTML file.
- *async*, browser parses the HTML and JS together, only pausing to pausing to process the script
- With the *defer* attribute, the browser parses and loads the HTML, then processes the script

**Class 3 (1/15/2025)**
- Functions, Data Types, and Operators
Function: a programming structure consisting of a collection of statements that share a common purpose or calculate a value

- Syntax for a *named* function:
function functionName(parameters) {
statements
}
- Syntax for an *anonymous* function:
function (parameters) {
statements
}

- Using event handlers
• Most direct method of associating a function with an event
• Drawback: places JavaScript code in the HTML file
• Syntax for creating an event handler as an attribute of the HTML element:
<elem onevent = "function()"> </elem>

- Events as object properties
• Places the event handler within the JavaScript code file
• Can only specify function name, not parameter values
• Only one function can handle an event at a time
• Syntax for an event as an object property:
object.onevent = function;

- Event listeners
• An event listener listens for an event as it propagates through a web page, during either:
• The capture phase (event moves down the object hierarchy) OR
• The bubbling phase (event moves back up the object hierarchy)
• Can attach multiple functions to the same event
• Syntax for method that attaches an event listener to an object:
object.addEventListener("event", function, capture)

- Events and anonymous functions
• Include entire structure of anonymous function in place of function name in an event handler or event listener
• Can pass in parameter values with this approach
e.g: document.getElementById("submit").addEventListener("click", function () {
  document.getElementById("submit");
  var length = document.getElementById("length").value;
  var width = document.getElementById("width").value;
  var height = document.getElementById("height").value;
  var volume = length * width * height;
  document.write(volume);
});

- Scope: where a variable or function can be called within the program
• Variable/function is only recognized within scope
• Referencing elsewhere results in an error
• let and var declaration scopes
• Variables declared with *let* are block scoped: scope is limited to the command block
• Variables declared with *var* are function scoped: scope is limited to the function
- Local and global scope
• Variables/functions with local scope (e.g., local variables) are accessible within the
command block or function where they are defined
• Includes block scope and function scope
• Those with global scope (e.g., global variables) are defined outside a block/function
and thus accessible throughout the program

• Can create local and global variables with the same name but different values
• Local variable takes precedence when in scope
• Assigning a value to the local variable does not affect the global variable’s value outside the local variable’s scope
• Global variables most useful for small applications and variables used as constants
• Local variables preferable for values used within and changed by functions

- Data Types
• Strongly typed (statically typed) programming languages require that you declare the
type of data that a variable contains and do not allow you to alter that type
• Loosely typed (duck typed, dynamically typed) programming languages do not require
you to declare the data type and allow data types to be change
- JavaScript is loosely typed
• Data types cannot be declared when variables are created
• JavaScript interpreter determines and assigns or reassigns the variable’s data type
based on the type of data stored
diffTypes = "Hello World!"; // String
diffTypes = 8; // Integer number
diffTypes = 5.367; // Floating-point number
diffTypes = true; // Boolean
diffTypes = null; // Null

**Class 4 (1/16/2025)**
- Unary operator: requires just a single operand either before or after the operator
Two types of unary operators:
• *Prefix operators*, which are placed before the variable
• *Prefix operator* is applied before assignment operator:
let x = 5;
let y = ++x // x = 6 and y = 6

• Postfix operators, which are placed after the variable
• Postfix operator is applied after assignment operator:
let x = 5;
let y = x++ // x = 6 and y = 5

*Conditional operators (ternary operators)* return one of two possible values given the
Boolean value of comparison
• Syntax: condition ? trueValue : falseValue;
• Falsy values, equivalent to false: "" (empty string), -0, 0, NaN, null, undefined
• Everything else is a truthy value, equivalent to true
• Can often use truthy and falsy values to make comparison operations more compact by
omitting the comparison operator

*Associativity* determines precedence for operators with equal intrinsic precedence
Left to right:
30 / 5 * 2 evaluates to 12

Right to left: 
let x = 3;
let y = 2;
x = y x= ++x; // Value of both x and y is 8

innerHTML = gets or sets the HTML contained within the element

**Class 5 (1/22/2025)**
- Arrays and Controlling Flow

• Syntax for creating an array with an array literal (values as a comma-separated list, or no
values to initialize an empty array):
let array = [values];
• Syntax for creating an array with the new Array() object constructor:
let array = new Array(values)
let array = new Array(length)
