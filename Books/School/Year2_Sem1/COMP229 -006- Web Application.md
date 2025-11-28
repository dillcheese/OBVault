---
lastSync: Wed Nov 26 2025 11:54:00 GMT-0500 (Eastern Standard Time)
---
No finals (Group Project)
1 mid term
4 assignments 
quizzes

## Learned Stuff

**MERN** 
MongoDB (noSQL db)
Express (middle ware)
React (frontend- client side)
Node (backend- server side)


A record in MongoDB is called a **document** (equivalent to a row in relational DBs).
MongoDB stores documents in **collections** (equivalent to tables in relational DBs).


## Week 1 (Sept 3 2025)

**MERN** 
MongoDB (noSQL db)
Express ()
React (frontend)
Node (backend)
All 4 are JavaScript based and have inherent integration 

<u>Node.js:</u> JavaScript runtime environment
Event Driven
Async (parallel functioning)
Npm = node package manager
Yarn = more recent package manager

- It's asynchronous, thus allowing your app to run and respond to other events while handling a long-running task. This feature provides an improved user experience.
- Run on single-thread architecture meaning all requests are executed in the same thread, unlike traditional servers such as Apache HTTP that create limited threads to process requests. This way, Node.JS can process more requests than its counterparts.

<u>Express:</u>  Middleware (HTTp request-response pipeline)
Maintains the use of JavaScript between front and backend

<u>MongoDB:</u> document-oriented database that stores data in flexible, JSON- like documents.
Known for availability and scalability

Sharding (geographic separation/database separation. Asia has its own DB, so does NA etc.)

Schema-less DB (can choose to get specific info from entries in database)

Choosing MongoDB as the database for a Node and Express web application will make a fully JavaScript-based and  
standalone server-side application.

<u>React:</u> component-based JavaScript.
Can us typescript (need to install)
Write it once and us it in multiple pages in a site.

React changes based on user changes (don't have to reload)

Pros and cons of MERN stack

- Offers native experience to users
React, as part of the MERN stack, enables businesses to build robust hybrid mobile apps using React Native framework. This framework is dedicated entirely to building mobile applications. As such, it supports features such as camera access and seamless data sync between the offline and online states of the app (basically allows oyu to writ code onc and make a sit for PC and mobile). 


**MEAN Structure** 

MEAN and MERN stacks are popular technology stacks for web application development.

Th same as MERN except it replaces React with Angular.

![[Pasted image 20250903104845.png]]

<u>Angular:</u> Frontend built by Google. 

Angular enables developers to extend their HTML tags with metadata for a more dynamic and interactive web experience, compared to extending them with static HTML and JavaScript or jQuery. The framework has other perks, such as form validation and back-end communication.

Angular's unique features include the following:
- Compatible with most browsers
- Uses Typescript syntax (JavaScript is not a type like int, string etc., but Typescript has support)
- Uses the MVC architecture
- Animation support
- It offers advanced testing tools, for example, Karma and Jasmine.

MEAN stack

- Uses Angular for the frontend

- Has a steeper learning curve

- Offers good developer productivity for fast deployment (for devs who are familiar with the framework)

- Lower performance in UI rendering

- Usually preferred for large-scale apps because of its opinionated and standardised approach.

- Angular uses two-way data binding

- Supports hybrid mobile app development, but there’s no Angular framework for building native apps.

MERN stack

- Uses React library for the frontend

- Relatively easy to learn and has a large pool of developer talent

- Lowers productivity because there’s a need for 3rd party tools, resulting in less rapid development

- Quicker response time

- Often used for building single-page applications

- React uses a unidirectional data flow

- It has a dedicated framework, React Native, for building hybrid mobile applications.

MERN is slightly more popular than MEAN (React over Angular)

**JavaScript**
const keyword
A constant is a variable that cannot be overwritten. Once  
declared, you cannot changes it’s value. A lot of the variables  
that we create in JavaScript should not be overwritten, so we’ll  
be using const a lot. Like other languages had done before it,  
JavaScript introduced constants with ES6.  
Before constants, all we had were variables, and variables  
could be overwritten:  
var pizza = true;  
pizza = false;  
console.log(pizza); // false

let keyword
In JavaScript, we create code blocks with curly braces ({}).  
In functions, these curly braces block off the scope of any  
variable declared with var.  
On the other hand, consider if/else statements. If you’re  
coming from other languages, you might assume that these  
blocks would also block variable scope. This was not the case  
until let came along.

With the let keyword, we can scope a variable to any code  
block. Using let protects the value of the global variable:  
var topic = "JavaScript";  
if (topic) { let topic = "React";  
console.log("block", topic); // React  
}  
console.log("global", topic); // JavaScript  
The value of topic is not reset outside of the block.

You can change the variable value if you use let

Template Strings
Template strings provide us with an alternative to string  
concatenation. They also allow us to insert variables into a  
string. You’ll hear these referred to as template strings,  
template literals, or string templates interchangeably.  
Traditional string concatenation uses plus signs to compose a  
string using variable values and strings:  
var lastName = "Smith";  
var firstName = "John";  
var middleName = "Doe";  
console.log(lastName + ", " + firstName + " " + middleName);

With a template, we can create one string and insert the  
variable values by surrounding them with ${ }:  
var lastName = "Smith";  
var firstName = "John";  
var middleName = "Doe";  
console.log(`${lastName}, ${firstName} ${middleName}`);  
Any JavaScript that returns a value can be added to a template  
string between the ${ } in a template string.


Functions
A function declaration or function definition below starts with  
the function keyword which is followed by the name of the  
function log Compliment. The JavaScript statements that are  
part of the function are defined between the curly braces.  
function logCompliment() {  
console.log("You're doing great!");  
}  

Function return

A return statement specifies the value returned by the  
function.  
const createCompliment = function(firstName, message) {  
return `${firstName}: ${message}`;  
};  
createCompliment("Molly", "You're so cool");  
If you wanted to check to see if the function is executing as  
expected, just wrap the function call in a console.log:  
console.log(createCompliment("You're so cool", "Molly"));


Arrow functions

Arrow functions are a useful new feature of ES6. With arrow  
functions, you can create functions without using the function  
keyword. You also often do not have to use the return  
keyword. Let’s consider a function that takes in a firstName and  
returns a string, turning the person into a Lord. Anyone can be  
a Lord.  
const lordify = function(firstName) {  
return `${firstName} of Canterbury`;  
};  
console.log(lordify("Dale")); // Dale of Canterbury  
console.log(lordify("Gail")); // Gail of Canterbury

With an arrow function, we can simplify the syntax  
tremendously:  
const lordify = firstName => `${firstName} of Canterbury`;  
With the arrow, we now have an entire function declaration on  
one line. The function keyword is removed. We also remove  
return because the arrow points to what should be returned.  
Another benefit is that if the function only takes one argument,  
we can remove the parentheses around the arguments.  
More than one argument should be surrounded by  
parentheses:

// Typical function  
const lordify = function(firstName, land) {  
return `${firstName} of ${land}`;  
};  
console.log(lordify("Dee", "yui"));  
// Arrow Function  
const lordify = (firstName, land) => `${firstName} of ${land}`;  
console.log(lordify("Don", "Piscataway")); // Don of Piscataway  
console.log(lordify("Todd", "Schenectady")); // Todd of  
Schenectady


Destructuring Objects
Destructuring assignment allows you to locally scope fields  
within an object and to declare which values will be used.  
Consider the sandwich object. It has four keys, but we only  
want to use the values of two. We can scope bread and meat to  
be used locally:  
const sandwich = {  
bread: "dutch crunch",  
meat: "tuna",  
cheese: "swiss",  
toppings: ["lettuce", "tomato", "mustard"]  
};  
const { bread, meat } = sandwich;  
console.log(bread, meat); // dutch crunch tuna

**Spread Operator**
The spread operator is three dots (...) that perform several different tasks. First,  
the spread operator allows us to combine the contents of arrays. For example, if we  
had two arrays, we could make a third array that combines the two arrays into one:  
 
const peaks = ["Tallac", "Ralston", "Rose"];  
const canyons = ["Ward", "Blackwood"];  
const tahoe = [...peaks, ...canyons];  
console.log(tahoe.join(", ")); // Tallac, Ralston, Rose, Ward, Blackwood  
  
  
  
All of the items from peaks and canyons are pushed into a new array called tahoe.







## Week 2 (Sept 8)
Version Control and First React Project

3rd generation of version control: current
- Decentralized in nature

**React**
  
Functional Components: Functional components are simply JavaScript functions.


State Management: Counters and Timers are reliant on state management

Hooks start with word 'use' (useState, useReact etc.)

The useState Hook is the most basic API provided by React to interact with state.  
useState is React Hook that allows you to add state to a functional component.  
It returns an array with two values: the current state and a function to update it.  
The Hook takes an initial state value as an argument and returns an updated state value whenever the setter function is called.  
It can be used like this:  \

const [state, setState] = useState(initialValue);  

Here, the initialValue is the value you want to start with,  
 and state is the current state value that can be used in your  
component.  
The setState function can be used to update the state, triggering a  
re-render of your component.


Class 2: Work Period




## Week 3 (Sept )

### Class 1: 

Node Quiz due Sept 21

React Router: handles routing and navigation in a webpage

BrowserRouter:  Uses the HTML5 history API to keep your UI in sync with the URL.
HashRouter: Uses the hash portion of the URL (i.e., window.location.hash) to keep your UI in sync with the URL.

Whenever you have one or more Route, you'll most likely   want to wrap them in a Routes.  
import { Routes, Route } from "react-router-dom";  
function App() {  
return (  
<Routes>  
<Route path="/" element={<Home />} />  
<Route path="/about" element={<About />} />  
<Route path="/settings" element={<Settings />} />  
<Route path="*" element={<NotFound />} />  
</Routes>  
);  
}

Link Component: 
Link: Creates navigational links in your application.  
NavLink: Similar to Link but provides additional styling attributes when the link is active

Protected Routes: 

**React Forms**
Textboxes, Radio Buttons etc.
In React, there are two ways of handling form data:  

•*Controlled Components*: In this approach, form data is handled by React through the use of hooks such as  the useState hook.  

In React, a controlled component is a component where form elements derive their value from a React state (useState hook).  

When a component is controlled, the value of form elements is stored in a state, and any changes made to the value are immediately reflected in the state.  

To create a controlled component, you need to use the value prop to set the value of form elements and the onChange event to handle changes made to the value. 

The value prop sets the initial value of a form element, while the onChange event is triggered whenever the value of a form element changes. Inside the onChange event, you  
need to update the state with the new value using a state update function.

React forms use key value pairs.

•*Uncontrolled Components:* Form data is handled by the Document Object Model (DOM) rather than by React. The  DOM maintains the state of form data and updates it based  on user input.

Uncontrolled components in React refer to form elements whose state is not managed by React. Instead, their state is handled by the browser's DOM.  

For instance, let's say you have a form that consists of a text input field, a select box, and a checkbox. In a controlled component, you would create a state for each form element  and write event handlers to update the state whenever the user interacts with any of the form elements.  

In contrast, an uncontrolled component allows the browser to handle the form elements' state. When a user enters text into a text input field or selects an option from a select box, the browser updates the DOM's state for that element automatically.

After importing the useForm hook, you can invoke it to get access to the functions and properties that it provides:  
const { register, handleSubmit, formState:{errors} } = useForm();  
In the above code, we're using destructuring to extract the register, handleSubmit, and errors properties from the useForm hook.

(Quiz Stuff)
**Node.js**
Asynchronous JavaScript and XML (AJAX) technology a few years earlier transformed static websites into dynamic web applications, but the fundamental building block  
of web development didn't follow this trend.

Ryan Dahl created Node.js. He took the V8 engine, wrapped it with the already solid C code,  and created the first version of Node.js


**Npm**
Node.js is a platform, which means its features and APIs are kept to a minimum.  
To achieve more complex functionality, it uses a module system that allows you to extend the platform.  
The best way to install, update, and remove Node.js modules is using npm.  
npm is mainly used as:  
➢ A registry of packages for browsing, downloading, and installing third-party modules  
➢ A CLI tool to manage local and global packages  
NPM is installed during the Node.js installation process

install -g (global install)
npm install Package Unique Name@Package Version 
npm install express@2.x

The package.json file is basically a JSON file that contains the different attributes you'll need to describe your application properties.

**Node.js Web Apps**

There are many modules to support web application development, but none as popular as the Connect module.  

The Connect module delivers a set of wrappers around the Node.js low-level APIs to enable the development of rich web application frameworks. 
Simple Node.js server:

server.js
const http = require('http');  
http.createServer((req, res) => {  
res.writeHead(200, {  
'Content-Type': 'text/plain'  
});  
res.end('Hello World');  
}).listen(3000);  
console.log('Server running at  
http://localhost:3000/');

**Connect**
Connect is a module built to support the interception of requests in a more modular approach.  
❑ In the first web server example, you learned how to build a simple web server using the http module.  
❑ If you wish to extend this example, you'd have to write code that manages the different HTTP requests sent to your server, handles them properly, and provides the correct response to each request.

Connect uses a modular component called *middleware*, which allows you to simply register your application logic to predefined HTTP request scenarios.
Connect middlewares are basically *callback functions*, which get executed when an HTTP request occurs.  
❑ The middleware can then perform some logic, return a response, or call the next registered middleware.  
❑ While you will mostly write custom middleware to support your application needs, Connect also includes some common  
middleware to support logging, static file serving, and more.  
❑ The way a Connect application works is using an object called *dispatcher*.
The dispatcher object handles each HTTP request received by the server and then decides the order of middleware execution in a cascading form.

Connect middleware is basically a *JavaScript function with a unique signature*.
Each middleware function is defined with the following three arguments:  
➢ req: This is an object that holds the HTTP request information  
➢ res: This is an object that holds the HTTP response information and allows you to set the response properties  
➢ next: This is the next middleware function defined in the ordered set of Connect middleware

As you may have noticed, the middleware you registered responds to any request, regardless of the request path.  
❑ This does not comply with modern web application development because responding to different paths is an integral part of all web applications.  
❑ Fortunately, Connect middleware supports a feature called *mounting*, which enables you to determine which request path is required for the middleware function to get executed.  
❑ Mounting is done by adding the path argument to the app.use() method.


### Class 2: 

**Express**

The Express framework is a small set of common web application features, kept to a minimum in order to maintain the Node.js style
Built on top of Connect

Its features extend Connect to allow a variety of common web applications' use cases, such as the inclusion of modular HTML template  
engines, extending the response object to support various data format outputs, a routing system, and much more

Express presents three major objects that you'll frequently use.  
➢ The *application* object is the instance of an Express  application you created in the first example and is usually used to configure your application.  
➢ The *request* object is a wrapper of Node's HTTP  request object and is used to extract information about the currently handled HTTP request.  
➢ The *response* object is a wrapper of Node's HTTP response object and is used to set the response data and headers

*Response object:* The response object is frequently used when developing an Express application because any request sent to the server will be handled and responded using the response object methods.


**MVC Pattern (model view controller)**

The Express framework is pattern agnostic, which means it doesn't support  
any predefined syntax or structure as do some other web frameworks.  

Applying the MVC pattern to your Express application means that you can  
create specific folders where you place your JavaScript files in a certain  
logical order.


**Folder Structure**

*Assets:* The assets folder contains all images, icons, CSS files, font files, etc. that will be used in your web application. Custom  images, icons, paid fonts are being placed inside this folder.

*Context:*  
When using React Js as your preferred frontend UI library,  
the context folder stores all your react context files that are  
used across components and multiple pages.


*Components:* The components folder holds the UI for your application. It  
contains all our UI components like navbar, footer, buttons, modals, cards, etc.

*Data:*  The data folder is used for storing text data which will be used in different sections and pages as JSON files.
Doing this will enable updating of information easier.

In a JavaScript context, "type": "module" is a property you can add to your package.json file.

*Example:*
"name": "mern_skeleton",
  "version": "1.0.0",
  "type": "module",

When you specify "type": "module":  
1. Imports and Exports: You can use import and export statements instead  
of require() and module.exports.  

*e.g:* //module.exports = app;
export default app;

import router from "./server/assets-router.js";
//const assetsRouter = require("./server/assets-router");

2. File Extensions: You typically need to use file extensions (like .js or .mjs) when importing local modules.  
3. Top-level await: You can use the await keyword at the top level of your module.  

This change helps you take advantage of modern JavaScript features and improves compatibility with browser environments that support ESM.

## Week 4 (Sept 22)
### Class 1

**Intro to MongoDB and NoSQL**
The growth of Web raised the need for larger, more scalable storage solutions.  
➢ a variety of key-value storage solutions were designed for better availability, simple querying, and horizontal scaling.  
❑ This new kind of data store became more and more robust, offering many of the features of the relational databases.  
❑ Different storage design patterns emerged, including *key-value* storage, *column* storage, *object* storage, and the most popular one, *document storage*.

**relational vs document-oriented**
In a common relational database, data is stored in different tables, often connected using a primary to foreign key relation.  
A program will later reconstruct the model using various SQL statements to arrange the data in some kind of hierarchical object representation.  
Document-oriented databases handle data differently.  
➢ Instead of using tables, they store hierarchical documents in standard formats, such as JSON and XML.

**Document-oriented DB example**
In a *document-based* database, the blog post will be stored completely as a single document that can later be queried.
Document is basically a set of key value pairs.
For instance, in a database that stores documents in a JSON format, the blog post document would probably look like the following code snippet:  
{  
"title": "First Blog Post",  
"comments": [  
]  
}  
This model will allow faster read operations since your application won't have to rebuild the objects with every read.

Created in 2007 by Dwight Merriman and Eliot Horowitz
MongoDB was able to support complex data storage, while maintaining the high-performance approach of other NoSQL stores.

JSON-like storage format named *BSON* (BinaryJSON)
- a document consists of a list of elements, each with a string typed field name and a typed field value.  
➢ These documents support all of the JSON specific data types along with other data types, such as the Date type.  
➢ use of the _ id field as primary key -
The _ id field  value will usually be a unique identifier type, named ObjectId, that is either generated by the  
application driver or by the mongod service.  
➢ If driver fails to provide a _ id field with a unique ObjectId, the mongod service will add it automatically.

Dynamic schema in MongoDB makes polymorphism easier for applications.
A _replica set_ in MongoDB is a group of [`mongod`](https://www.mongodb.com/docs/manual/reference/program/mongod/#mongodb-binary-bin.mongod) processes that maintain the same data set. Replica sets provide redundancy and [high availability](https://www.mongodb.com/docs/manual/reference/glossary/#std-term-high-availability), and are the basis for all production deployments.

*SCRAM-SHA-1* and *MongoDB Challenge and Response (MONGODB-CR)* are client and user authentication mechanisms in MongoDB.

MongoDB supports searching by Fields, Range queries and Regular expression searches


**MongoDB sharding** 
Scaling is a common problem with a growing web application.  
*Scaling* refers to increasing the capacity of a database to handle growing workloads, traffic, and data volume efficiently.  
MongoDB natively supports horizontal scaling using sharding, making it ideal for big data applications and high-throughput systems.  
MongoDB provides two primary types of scaling  
• Horizontal Scaling (*Sharding*) – Expands capacity by adding more servers to distribute the load.  
• Vertical Scaling (*Upgrading Hardware*) – Increases the resources (CPU, RAM, Storage) of a single server.

**Mongoose**
Mongoose is a MongoDB object modeling tool that provides a schema-based solution to model application  
data. It includes built-in type casting, validation, query building, and business logic hooks.

Using Mongoose with this backend stack provides a higher layer over MongoDB with more functionality, including mapping object models to database documents.


## Week 5 (Sept 29)

### Class 1 (Theory)

**MVC Framework**
The Model-View-Controller (MVC) framework is an architectural/design pattern that separates an application into *three main logical components* Model, View, and Controller. Each architectural component is built to handle specific development aspects of an application. 
It isolates the business logic and presentation layer (frontend and backend) from each other. It was traditionally used for desktop graphical user interfaces (*GUIs*). 
Nowadays, MVC is one of the most frequently used industry-standard web development frameworks to create scalable and extensible projects. 
It is also used for designing mobile apps.

MVC was created by Trygve Reenskaug. The main goal of this design pattern was to solve the problem of users controlling a  
large and complex data set by splitting a large application into specific sections that all have their own purpose.

**Features of MVC:**  
• It provides a clear separation of business logic, UI logic, and input logic.  
• It offers full control over your HTML and URLs which  makes it easy to design web application architecture.  
• It is a powerful URL-mapping component using which we can build applications that have comprehensible and searchable URLs.  
• It supports Test Driven Development (TDD).

> [!info]+ Visual Representation of MVC
>
>![[Pasted image 20250929164151.png]]
> 
>  


*Controller:*  
❑ The controller is the component that enables the interconnection between the views and the model so it  
acts as an intermediary. The controller doesn’t have to worry about handling data logic, it just tells the model  
what to do. It processes all the business logic and incoming requests, manipulates data using the Model component, and interact with the View to  
render the final output.

*View:*  
❑ The View component is used for all the UI logic of the application.
It generates a user interface for the user. Views are created by the data which is collected  
by the model component but these data aren’t taken directly but through the controller. It only interacts with the controller.  

*Model:*  
❑ The Model component corresponds to all the data-related logic that the user works with. This can  
represent either the data that is being transferred between the View and Controller components or any  
other business logic-related data. It can add or retrieve data from the database. It responds to the controller’s  
request because the controller can’t interact with the database by itself. The model interacts with the database and gives the required data back to the  
controller.

*CRUD* 
Create
Read
Update
Delete

*CRUD-REST API*
The user routes that are defined in the user.routes.js file will use express.Router() to define route paths with  
the relevant HTTP methods and assign the corresponding controller function that should be called  
when these requests are received by the server.


lodash is a JavaScript library that provides utility functions for common programming tasks, including the  
manipulation of arrays and objects.


Postman (if you have no frontend)

**HTTP Request**
As you know, HTTP is a message-passing protocol, between two endpoints. 
One end will send a request, and the other will send a response.

GET, POST, PUT, DELETE


Midterm = Similar to Assignment 2

Make your own database
Screenshots of actions
screenshot of before and after actions (like deleting)
Successful response and failure 


> [!FAQ]+ Expanded
> sd
>  


Midterm: part 2 of assignment 1 like a2

Use database to connect to our database
Do a bunch of API calls (delete, post, )

Do a before and after screenshot
Screenshot of error states and success states


## Week 6 (Oct 6)

### Class 1:

Midterm done in class (2 hours, entire class time), Open book (can use slides)

**Authorization**
Auth with JSON Web Tokens

To restrict and protect access to user API endpoints according to the skeleton features, the backend will  
need to incorporate authentication and authorization  
mechanisms.  
There are a number of options when it comes to implementing user auth for web applications.  
The most common and time-tested option is the use of  
sessions to store user state on both the client and server-side.  
But a newer approach is the use of JSON Web Token (JWT) as a stateless authentication mechanism that  
does not require storing user state on the server side.
Both approaches have strengths for relevant real-world use cases.  
❑ However, for the purpose of keeping the code simple in  
and because it pairs well with the MERN stack and our  
example applications, we will use JWT for auth  
implementation.  


**JWT**
The password string that's provided by the user is not stored directly in the user document. Instead, it is handled as a virtual field.  


The encryption logic and salt generation logic, which are used to generate the hashed_password and salt  
values representing the password value, are defined as UserSchema methods.


The UserSchema methods can be used to provide the following functionality:  
❑ authenticate: This method is called to verify sign-in  
attempts by matching the user-provided password text  
with the hashed_password stored in the database for a specific user.  
❑ encryptPassword: This method is used to generate an  
encrypted hash from the plain-text password and a  
unique salt value using the crypto module from Node.  
❑ makeSalt: This method generates a unique and random  
salt value using the current timestamp at execution and Math.random().


The crypto module provides a range of cryptographic functionality, including some standard cryptographic hashing algorithms.  
❑ In our code, we use the SHA1 hashing algorithm and  
createHmac from crypto to generate the cryptographic HMAC hash from the password text and salt  
pair.Hashing algorithms generate the same hash for the same input value.  
❑ But to ensure two users don't end up with the same  
hashed password if they happen to use the same password text, we pair each password with a unique  
salt value before generating the hashed password for each user.

This will also make it difficult to guess the hashing algorithm being used because the same user input is  
seemingly generating different hashes.  
❑ These UserSchema methods are used to encrypt the user-provided password string into a hashed_password with a randomly generated salt value.  
❑ The hashed_password and the salt are stored in the user document when the user details are saved to the  
database on a create or update.  
❑ Both the hashed_password and salt values are required in order to match and authenticate a password string  
provided during user sign-in using the authenticate method. 


To restrict access to user operations such as user profile view, user update, and user delete, we will first  
implement sign-in authentication with JWT, then use it to protect and authorize the read, update, and delete routes.  
❑ The auth-related API endpoints for sign-in and sign-out will be declared in server/routes/auth.routes.js and then  
mounted on the Express app in server/express.js.

**Auth Routes**

The two auth APIs are defined in the auth.routes.js file using express.Router() to declare the route paths with  
the relevant HTTP methods.  
❑ They're also assigned the corresponding controller functions, which should be called when requests are  
received for these routes.  
The auth routes are as follows:  
❑ '/auth/signin': POST request to authenticate the user with their email and password  
❑ '/auth/signout': GET request to clear the cookie containing a JWT that was set on the response object after sign-in

A POST request to the signin route and a GET request to the signout route will invoke the corresponding  
controller functions defined in the auth.controller.js file next.


**Auth controller**
The auth controller functions in server/controllers/auth.controller.js will not only handle  
requests to the signin and signout routes, but also provide JWT and express-jwt functionality to enable  
authentication and authorization for protected user API endpoints.

The signout function clears the response cookie containing the signed JWT.  
❑ This is an optional endpoint and not really necessary for auth purposes if cookies are not used at all in the frontend.  
❑ With JWT, user state storage is the client’s responsibility, and there are multiple options for client-  
side storage besides cookies.  
❑ On signout, the client needs to delete the token on the client-side to establish that the user is no longer authenticated.

**Protecting Routes with express-jwt**
To protect access to the read, update, and delete routes, the server will need to check that the requesting
client is actually an authenticated and authorized user.  
❑ To check whether the requesting user is signed in and has a valid JWT when a protected route is accessed, we will use the express-jwt module.  
❑ The express-jwt module is a piece of middleware that validates JSON Web Tokens.

## Week 8 (Oct 27)
### Class 1: React Frontend to Complete MERN
A3: connecting backend from A2 to frontend from A1

Material UI: Styling Library


**Skeleton Frontend:**
*Home page:* A view that renders at the root URL to welcome users to the web application.  
*Sign-up page:* A view with a form for user sign-up,  
allowing new users to create a user account and  
redirecting them to a sign-in page when successfully  
created.  
*Sign-in page:* A view with a sign-in form that allows  
existing users to sign in so they have access to  
protected views and actions.  
*User list page:* A view that fetches and shows a list of  all the users in the database, and also links to individual user profiles.
*Profile page:* A component that fetches and displays an individual user's information.  
This is only accessible by signed-in users and also contains edit and delete options, which are only visible  if the signed-in user is looking at their own profile.  
*Edit profile page:* A form that fetches the user's information to prefill the form fields.  
This allows the user to edit the information and this form is accessible only if the logged-in user is trying to  
edit their own profile.  
*Delete user component:* An option that allows the signed-in user to delete their own profile after confirming their intent.
*Menu navigation bar:* A component that lists all the available and relevant views to the user, and also helps  
to indicate the user's current location in the application.

Homepage view:

The custom React components that we will create to make up the user interface will be accessed with the  
frontend routes specified in the MainRouter component.  
Essentially, this component houses all the custom views that have been developed for the application and  
needs to be given the theme values and routing features.  
This component will be our core component in the root App component, which is defined in the following code.


React Hooks

### Class 2: Code Along


#### Quiz: React Hooks

Hooks are just JavaScript functions

React handles data in two main ways:
- **State** → for internal, changeable data.
- **Props** → for external, read-only data passed from parent to child components.

Babel is often called a **compiler** because it converts code, but more precisely it’s a **transpiler**—it translates modern JavaScript (ES6+) into backward-compatible JavaScript. So both terms apply.


## Week 9

### Class 1: Theory
**Developing a Full-Stack system**

Users should be able to use the frontend views to fetch and modify user data in the database based on authentication and authorization.

**CRUD Operations**

**CREATE**
The create method will take user data from the view component, which is where we will invoke this method.  
Then, it will use fetch to make a POST call at the create API route, '/api/users', to create a new user in the backend with the provided data.
Returns the response from the server as a promise.

**LIST**
The list method will use fetch to make a GET call to retrieve all the users in the database, and then return the response from the server as a promise to the component.
The returned promise, if it resolves successfully, will give the component an array containing the user objects that were retrieved from the database.

**READ**
The read method will use fetch to make a GET call to retrieve a specific user by ID.  
Since this is a protected route, besides passing the user ID as a parameter, the requesting component must also provide valid credentials, which, in this case, will be a valid JWT received after a successful sign-in.

The JWT is attached to the GET fetch call in the Authorization header using the Bearer scheme, and  
then the response from the server is returned to the component in a promise.  
This promise, when it resolves, will either give the component the user details for the specific user or  
notify that access is restricted to authenticated users.  
Similarly, the updated user API method also needs to be passed valid JWT credentials for the fetch call, as  
shown in the next section.  

**UPDATE**
The update method will take changed user data from the view component for a specific user, then use fetch  
to make a PUT call to update the existing user in the backend.
This is also a protected route that will require a valid JWT as the credential.
As we have seen with the other fetch calls, this method will also return a promise containing the server's  
response to the user update request.

**DELETE**
The remove method will allow the view component to delete a specific user from the database and use fetch  
to make a DELETE call.  
This, again, is a protected route that will require a valid JWT as a credential, similar to the read and update  
methods.
The response from the server to the delete request will be returned to the component as a promise, as in the other methods.
In these five helper methods, we have covered calls to all the user CRUD-related API endpoints that we implemented on the backend.

Finally, we can export these methods from the api-user.js file as follows.

export {create, list, read, update, remove}

**Fetch for Auth API**
In order to integrate the auth API endpoints from the server with the frontend React components, we will add methods for fetching sign-in and sign-out API endpoints in the client/lib/api-auth.js file. Let's take a look at them.

SignIn


SignOut


import { signout } from "./api-auth.js";  
const auth = {  
isAuthenticated() {  
if (typeof window == "undefined") return false;   // check for a valid window
if (sessionStorage.getItem("jwt"))  //check session storage for jwt
return JSON.parse(sessionStorage.getItem("jwt"));   //return the token
else return false;  
},  
authenticate(jwt, cb) {  
if (typeof window !== "undefined")   // check for a valid window
sessionStorage.setItem("jwt", JSON.stringify(jwt));  
cb();  
},  
clearJWT(cb) {  
if (typeof window !== "undefined") sessionStorage.removeItem("jwt");  
cb(); //optional  callback
signout().then((data) => {  
document.cookie = "t=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;";  
});  
},  
};  
export default auth;


**Completing User Frontend**
*Users:* To fetch and list all users from the database to the view  
*Signup:* To display a form that allows new users to sign up  
*Signin:* To display a form that allows existing users to sign in  
*Profile:* To display details for a specific user after retrieving from the database
*EditProfile:* To display details for a specific user and allow authorized user to update these details  
*DeleteUser:* To allow an authorized user to delete their account from the application  
*Menu:* To add a common navigation bar to each view in the application.


useEffect (only when something changes is when a component is reloaded)

Menu

HOC (higher order component)
Pagination (different pages)

**Group Project**

Use GitHub

Use a Project Management tool (Jira or Trello)
Create a powerpoint

## Week 10

### Class 1 (Nov 10)
**Testing and Deploying a Full Stack App**



*express.js*
import path from "path";  
const CURRENT_WORKING_DIR = process.cwd();
app.use(express.static(path.join(CURRENT_WORKING_DIR, "dist/app")));

vite.config.js


Many sites to deploy apps

### Class 2
Work time for group project

## Week 11

### Class 1  (Nov 17)

CI/CD (Continuous Integration/ Continuous Development)

End to End Tests:


**Integration Tests:** Test the entire behaviour of the system

**Unit Tests:** Tests code for small isolated pieces  (single function)

Lint: checks for unnecessary imports, unused variables etc.

Playwright: Testing Framework/Software

1. Cross Origin Testing
2. 


## Week 12

**A4 + Group Project 4**
*Group*

Final release of project (error free)

Should be able to do unit testing and end to end testing

Video of pull requests in github?

*A4*
Write unit tests
Part 2 (can ignore)
Deploy onto cloud server


**Firebase + Auth?**

Backend data storage platform
Can deploy full stack without backend code


firebase.js code in custom folder in src folder


need to install firebase with npm


prop drilling (passing a component through many layers of code)



Unit test only 

no end to end testing


## Week 13




## Week 14











