
#Inception 


### Emit
Vs code uses Emit. 
Emit generates code inside vs code. 
`html:5` will give you the basic skeleton of html5.


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>


### Hello World using HTML

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0">
    <title>Namaste React 2024</title>
</head>
<body>
    <div id="root">
        <h1>Hello World</h1>
    </div>
</body>
</html>

### Hello world using JS
Lets use javascript to build this hello world. 
We use script tag. 

#### How to create H1 tag inside JS? 
We will use document.createElement.
This is the api that we will use to create the h1 tag. 

Lets get this tag inside normal variable constant
`const heading = document.createElement("h1");`
Let us put hello world insid this heading.
`heading.innerHTML = "Hello World from JS";`
Now we have to put this heading inside the root. 

Where is my root?
`const root = document.getElementById("root");`

Now we have to put in  this heading inside the root. The root will give refrence to the div tag. 
To put heading inside the div. There is a function in JS `appendChild`. 
`root.appendChild(heading):`

`appendChild` is there on every html node. 
This heading will go as child inside the root. . h1 will go as a child inside the root. 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0">
    <title>Namaste React 2024</title>
</head>
<body>
    <div id="root"></div>
    <script>
        const heading= document.createElement("h1");
        heading.innerHTML="Hello World from Javascript!";
        const root=document.getElementById("root");
        root.appendChild(heading);
    </script> 
</body>
</html>


### Hello World using React


How does browser understand what these document.createElement, innerHTML, document.getElementById?
Thesea are the superpowers that browsers have in in. Browsers have a JS engine in it that executes the Javascript. 
Does this browser have react? No browser do not understant react.
To use react, we have to get react into our project. 

Adding react via project. 
First way of injecting react is  using CDN. 
CDN is a content delivery network. 
These are the websites where react has been hosted and we are just pulling react from there into our project. 

There are CDN links. 
CDN is a place where react library is hosted. 
We are fetching that react and putting it in our code using CDN links. 

#### What is CDN? Why do we use CDN? HW

Include the CDN links inside script tag. 
Now our project has react inside it. Browser will understand react. 

#### What will be inside the CDN link? 
React.development.js  contains all react code written in plain Javascript. Full of variables and functions.
Facebook developers have written this react code.  
#### What is react?
React is JS library. React at the end of the day is just Javascript. 
#### What is Cross Origin? HW

As soon as I inject cdn in our project, we got something amazing. 
Go to console and type React and enter. 
The react that we injected is available to us for use. 

#### What is the second CDN file? 
react-dom.development. 
#### Why there are two files? 
react.development.js is the core of react. 
react dom is the react library which is useful for dom operations. It is useful for modifying dom. Like a bridge between react and dom. 
React does not only work on browsers, It also works on mobile phones.

### How to create H1 tag inside react?
In JS we used document.createElement. In react we use React.crateElement().
But the api is little different than Javascript. 
This createElement takes 3 arguments. 
1. What tag we need to create
2. An object 
3. What we have to put inside the h1 tag. 

`const heading = React.createElement("h1",{},"Hello World from React");`

Now we have to put this heading inside div with id="Root".

First we need to tell react where we need to render stuff up. 
React needs to have to root to do all the dom manipulation. 
We have to create Root. 
Creating an element is the core thing of react so it comes from first library react.development cdn link.
Crateing a root and rendering something inside it. It is a job of react dom. So it comes from second library.

Creating H1 element inside react 
`const heading=React.createElement("h1",{}, "Hello World from React");`
Putting h1 into dom, we use react dom library to create root method.
`const root = ReactDOM.createRoot(document.getElementById("root"));`
We have created a root for our react library. Whatever we  do we can render this heading inside that root.
`root.render();`
what we have to render inside root? 
`root.render(heading);`
Root is the place where all the react code will run. Everything that we will render, we will render inside this root. 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"/>
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0"/>
    <title>Namaste React 2024</title>
</head>
<body>
    <div id="root"> </div>
    <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script>
        const heading= React.createElement("h1",{},"Hello World from React");
        const root = ReactDOM.createRoot(document.getElementById("root"));
        root.render(heading);
    </script>
   
</body>
</html>

Lets create a new JS file to write all our react code. 
Let me put it inside app.js file. 
Inject app.js to our file. 

App.js
const heading = React.createElement("h1",{},"Hello World from React");
const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(heading);

Index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"/>
    <meta name="viewport" content="width=640, initial-scale=1.0"/>
    <title>Namaste React 2024</title>
</head>
<body>
    <div id="root"> </div>
    <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="./App.js"></script>
   
</body>
</html>

REact was built to manipulate our dom using javascript. 
Most costly operation in our webpage is dom tree getting changed. Adding some nodes or removing some nodes from dom is the costly operation. 
Whever we need to do anything on the webpage, do it with javascript.


What is the object parameter?
 `const heading= React.createElement("h1",{},"Hello World from React");`
 The object that we have. This object is a place where we give attributes to our tag. 
 If my h1 tag needs to have id="heading" or class="heading" 
 Whatever we pass in inside that object will be the attributes of that tag. 

 `const heading= React.createElement("h1",{id:"heading"},"Hello World from React");`


 What is React.createElement? 

 console.log(heading);
 console will show us an object. 

 What is React element>?
 It is nothing but a normal JS object. React.createElement creates an object for us.

 What is props? 
 Props are children and attributes that we pass in. which will go inside our tag. 

root.render(heading), render method is responsible for converting the object into H1 tag and putting it up on the dom. 


### Part 4
Our html is nested with  one tag inside another. 
How to create this type of structure inside react. 
To create nested elements with id.

/*
<div id="parent">
    <div id="child">
        <h1></h1>
    </div>
</div>

*/

const parent = React.createElement("div",{id:"parent"},React.createElement("div",{},React.createElement("h1",{},"I am H1 tag")));


<div id="parent">
    <div id="child">
        <h1></h1>
    </div>
</div>


const parent = React.createElement(
  "div",
  { id: "parent" },
  React.createElement(
    "div",
    { id: "child" },
    React.createElement("h1", {}, "I am H1 tag")
  )
);
const heading = React.createElement(
  "h1",
  { id: "heading" },
  "Hello World from React"
);
const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(parent);

Creating Siblings 

3rd argument is children. This can be a single child or array or children.


/*
<div id="parent">
    <div id="child">
        <h1></h1>
        <h2></h2>
    </div>
</div>
*/
const parent = React.createElement(
  "div",
  { id: "parent" },
  React.createElement("div", { id: "child" }, [
    React.createElement("h1", {}, "I am H1 tag"),
    React.createElement("h2", {}, "I am H2 tag"),
  ])
);
const heading = React.createElement(
  "h1",
  { id: "heading" },
  "Hello World from React"
);
const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(parent);



If we have to create the following structure


/*
<div id="parent">
    <div id="child">
        <h1></h1>
        <h2></h2>
    </div>
    <div id="child">
        <h1></h1>
        <h2></h2>
    </div>
</div>
*/
const parent = React.createElement("div", { id: "parent" }, [
  React.createElement("div", { id: "child" }, [
    React.createElement("h1", {}, "I am H1 tag"),
    React.createElement("h2", {}, "I am H2 tag"),
  ]),
  React.createElement("div", { id: "child2" }, [
    React.createElement("h1", {}, "I am H1 tag"),
    React.createElement("h2", {}, "I am H2 tag"),
  ]),
]);
const heading = React.createElement(
  "h1",
  { id: "heading" },
  "Hello World from React"
);
const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(parent);



This is a mess when it gets big. So we have JSX. 
React is only written using JSX. 
JSX will make our life easy when we have to create tags. 
This is the last time we are using React.createElement. 
When we do modern react development, React 18 stuff, We will use JSX. 


Part 5
We have written some codes. Will the order of file matter? 
It will throw error if we do it in wrong order. 

The order of these files are always in sequence. 

What is cross origin? 
We have development and production links separately in CDN. Why do we have two types? 
What is root.render? It just puts something inside root tag. 
What if the root has some other thing already in root tag? It will be replaced by parent.


Order Matters 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"/>
    <meta name="viewport" content="width=640, initial-scale=1.0"/>
    <title>Namaste React 2024</title>
</head>
<body>

    <div id="root">
        <h1>I'm here</h1> 
    </div>
    <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="./App.js"></script>
   
</body>
</html>


I'm here gets replaced to Parent child in fraction of seconds. Why? 
Because of order of exectution. 
First dom prints I'm here. 
Then it calls react libraries. Goes to App.js and executes line by line. 
When it reaches root.render(parent), now everything inside root gets replaced. 
It will be replaced not appended. 
If you refresh and see, you can see both displaying and changes in fraction of millisecond. 


What if I have some more tags on top or bottom of root div tag. 
Will it now get replaced? No these will stay.
React is only working inside my div id root. 

React can work only in header, or body or footer. wherever the root is. 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"/>
    <meta name="viewport" content="width=640, initial-scale=1.0"/>
    <title>Namaste React 2024</title>
</head>
<body>
    <div id="header">
        <h1>Header</h1>
    </div>
    <h1>Im on top of root</h1>
    <div id="root">
        <h1>I'm here</h1> 
    </div>
    <h1>Im on bottom of root</h1>
    <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="./App.js"></script>
   
</body>
</html>



const root = ReactDOM.createRoot(document.getElementById("header"));
root.render(parent);


React can work in existing app as well. React can be injected easily in small portion of our app. React is a libray and  is not a framework. This is the beauty of the amazing library. 

Order of files matter alot. 
Where is the root where we are rendering stuff. 

 

 Recap
 How to bring into our code. Using CdN links.
Extracted script to app.js
Created Element. React element is an object.
CreateRoot is responsible to create the root. 
Render method puts that object into our page. 
Create element api takes 3 arguments. 
tag,
attributes- in objects, 
children. (multiple children should be passed as an array)
Root.render will replace the root. 
Top or bottom of root. 
Top or bottom of the page, we can still use react. Rest of the html will remain the same. 
