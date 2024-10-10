Lot of processing should be done before pushing the code to production.
We need to do bundling,code splitting, chunking, image optimization,remove comments, minify, optimize and many more. 

When you create a create-react-app, it creates a scaffold for you. It will create an app which is already production ready. 
Lets see how to create our own create react app. 

Can react itself do the production ready app? No We need lot of other libraries, js etc to make our code scalable and ready. 

React is making our app fast but only to an extent. 
Lets see how to get those packages to our app. 
Let's see NPM.. What is the full form of NPM ? If you say it is node package manager, then it is wrong. 
NPM is everything but a node package manager. If you see the npm website, you can nowhere find node package manager. npm will have many different names with npm with random things. 

NPM does NOT have a FULL FORM. 

NPM manages packages but it does not stand for node package manager. 
NPM behind the scenes work as node package manager. 

NPM is a standard repository for all the packages. It is the biggest package manager. 
All the libraries, utilities comes from npm packages. 
When you create a create-react-app it will automatically configures npm. 
Lets do from scratch. 

Lets add npm to our project. 
'npm init' 
'npm init-y" will skip something so lets not do that. 
 
 Enter npm init in terminal. and enter the question that it asks like the following.

'PS D:\Shared\Namaste-React-2024> npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help init` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (namaste-react-2024)
version: (1.0.0)
description: This is Namaste React 2024
entry point: (App.js)
test command: jest
git repository: (https://github.com/AnnZoeFreelancer/Namaste-React-2024.git)
keywords: namaste react, 2024
author: Anitha Mohan
license: (ISC)
About to write to D:\Shared\Namaste-React-2024\package.json:

{
  "name": "namaste-react-2024",
  "version": "1.0.0",
  "description": "This is Namaste React 2024",
  "main": "App.js",
  "scripts": {
    "test": "jest"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/AnnZoeFreelancer/Namaste-React-2024.git"
  },
  "keywords": [
    "namaste",
    "react",
    "2024"
  ],
  "author": "Anitha Mohan",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/AnnZoeFreelancer/Namaste-React-2024/issues"
  },
  "homepage": "https://github.com/AnnZoeFreelancer/Namaste-React-2024#readme"
}


Is this OK? (yes)
PS D:\Shared\Namaste-React-2024> '


When we are done with our initialization, it creates a file in our project named 'package.json'

What is package.json?
This package.json file is a configuration for our npm. It has created in json structure. 

npm manages packages but it is also known as dependencies. 
our project is dependent on lot of packages. 

Let us install our dependencies. The most important package in our project is Bundler. 
What is a bundler? 
When you have a normal html, css, js. Our whole code needs to be compressed, cleaned, bundled. A bundler does this thing. 

Webpack, parcel, wheat are all budlers. \

Bundler basically bundles our app, packages our app. so that it can be shipped to production. 

When we use create-react-app it uses webpack bundler behind the scenes. 

In our project we are going to use parcel. 

How to get parcel? It comes as a node package. we wil install that package. 
Since we have npm, we can install parcel to our package. 
How to do that?
npm install parcel
We will also use -D 
npm install -D parcel 
What is this -D? 
There are two types of dependencies our app can have.
1. Dev dependencies
2. Normal dependencies

Dev is generally required in development phase. 
Normal dependencies is used in production also. 

Parcel is beast, it will do many things to our app. 
We go this in package.json 
 "devDependencies": {
    "parcel": "^2.12.0"

    The version of parcel is 2.12.0 
    What is the sign ^ means? carrot symbol has nothing to do with react but we can also put tilde ~ here. 

    suppose a new version of parcel is released, if you put this carror ^, it will automatically update the minor version in our app. 
    If we put tilde ~ it will release the major version . 

    Always keep ^ carrot over there because minor version are okay to update. Major version can affect the project. A lot of things will break in our app. 


    We have another file package-lock.json. What is this file? 
    
    what is package-lock.json? 
    package.json is a configuration of npm. It keeps the track of what version of package is installed in our system.  package.json can have a carror or tilde to update the minor or major versions. 
    package-lock.json keep a track of exact version that is being installed. It locks the version and keeps the record of it. 


    In parcel you can see, integrity, what is integrity?
    This is a hash sha hash. 
    Have you heard, it is working on local but it breaks on production? To avoid that, package-lock.json keeps a hashto verify whatever there is in my machine is the same version that is being deployed on to my production. It is a very important file. 

    

    There is one more folder created node_modules. It has so much code. What are these? 
    This node modules contains all the code that we fetch from npm. 
    When we install parcel, it fetches all the code of parcel and putting it inside node modules. 
    It is like database of all our packages and dependencies. 
    Node modules is very heavy, it fetches all the codes. 

    We just installed parcel, why we have many things inside node modules? 
    It came because our project needs parcel. Parcel as a project has its own dependencies. And those can have its own dependencies. This is known as transitive dependencies. 

    Parcel cant do all these things on its own. it needs to be dependent on many other dependencies. 
    Parcel uses babel. 

    How is parcel managing all these things? 
    In our whole project how many package.json and package-lock.json file do we have? one? NO 
    Every package has its own package and package-lock inside all node-modules folder. 
    It also has many dependecies. Like a dependency tree. 
    node modules is a collection of dependencies. 

    The size of node modules is huge. Should we put this node-modules to production or git? 
    Absolutely NO
    The best practice is to put this file in git ignore. This will ignore the files to not go into git or production. 

    Let us create a file .gitignore 
    /node_modules 
    this will ignore the node modules onto github.

    Why should we not put in git? 
    If we have package and package-lock.json, we can recreate all my node modules. Even if we delete the node modules, we can recreate all the node modules by entering 'npm install' on command prompt. 

    Should we put package and package-lock.json onto git? Absolutes YES 
    They maintain the exact version of each dependencies. 
     
    Whatever we can regenerate, dont put it on git. 


    Part 2
    We will use parcel to ignite our app. 
    npx parcel index.html

    npx means executing our package. 
    npx package-name wil execute that package. 
    index.html is the source.  Parcel will goes to the source index.html and build a development build for our app and host that development build in 1234. 
    
  Server running at http://localhost:1234

  Parcel is making our app running in port 1234. 


    How did we inject react into our app? we used cdn links. 
    Another way to get react into our app is via npm. 
    React at the end of the day is a js package. 

    We no longer have to do with the cdn links. It is not the preferred way to bring react to our app. Because it is a costly operation to call via cdn links. 
    If we have our code in node modules then it is easy to run. 
    If we get a newer version, we have to keep changing our url in cdn link. 
    If we have in package.json. it will be very easy to manage react. 

    Let us install react into our code. 
    npm install react

    We are not writing -D here, we want react as a normal dependency and not a dev dependency. 


To stop the terminal in VS Code, you can use the following keyboard shortcut depending on your operating system: Windows: Ctrl + Shift +C


npm install react 
WE got 18.3.1 in package.json file 


  "dependencies": {
    "react": "^18.3.1"
  } 

We got react in node modules also. 
Let us install react dom.
npm install react-dom
some use the following way. i is short form of install.
npm i react-dom 

Now we have react and react dom in our project. 

"dependencies": {
    "react": "^18.3.1",
    "react-dom": "^18.3.1"

Now we no longer need the cdn. Remove them.

Run the server. npx parcel index.html

It gives an error, react isnot defined. We have installed react but how to use it in our code. 
WE have to use keyword using import. 
import React from "react";
react refers to react inside our node modules. 

Once we import in app.js
import React from "react";
import ReactDOM from "react-dom";

When we run the file, we get this error 
@parcel/transformer-js: Browser scripts cannot have imports or exports.

What does it mean? 
The error is shown from parcel. 
Basically in our html , we are injecting our App.js. 
The import is not a normal javascript. Javascript doesn'tknow what import is. 
We need to tell the browser that it is not a normal browser file, it is a module. 

<script type ="module" src="./App.js"></script>

When we type module, it is not a normal browser script, it will be considered as a module. 
The error has gone. 
Now the import react is coming from node modules. not the cdn links. 

Parcel is a beast 
-Dev Build 
-Local Server 
-HMR(Hot module reloading)
It refreshes automatically when we change something. 
-File Watching Algorithm
Parcel uses a file watching algorith written in C++. It keeps a track of all the files. As soon as we save, it will build again. 
Build time gets reduced, why? Because parcel is caching things for us. 
-Caching - Faster Builds
.parcel-cache will have the cache files.We can delete the folder and restart it. It will build immediately. and is caching. 
-Image Optimization
Parcel is doing image optimization.The most expensive things in your browser page is to load images. 
What if we create a production build? It will minify our file. It will do bundling. It will compress the files also. It will remove white spaces and compress and ship it to production. 
-Minification
-Bundling
-Compress
-Consistent Hashing 
-Code splitting
-Differential Bundling 
when your app is hosted, your app can be opened inside internet explorer, older versions of interet explorer, firefox, phone etc. Parcel will do differential bundling.  So that your app runs smoothly in older browser support. 
-Error Handling 
-HTTPs
Parcel can be run in HTTPs also. 
-Tree Shaking 
Suppose we have 100s of functions in our code and we are using 4-5 functions, parcel will tree shake your files. It will remove unused code for you and run. 
-Different dev and production bundles
There are more optimization on production build and less optimization on dev build. 


To create a production build 
 before that enter
 npx parcel build index.html 

 you have to remover "main" from package.json file. Else you will get an error. Because npm automatically generated main app.js 
. So remove it. 

Where will this build go?
It all goes inside a new folder "dist" folder. 

What is dist?
When we execute npx parcel index.html, it generates a development build and puts it up into the dist folder. 

We can delete the dist, this folder can be generated automatically. 
When we build, dist will give three important files. one html file, one js file and one css file. Other files are for mapping. 
These 3 files will compress and minify everthing. 


.parcel-cache, dist, node modules are temperory folders. They can be regererated. 
These folders doesn't need in git hub. These can be put in git ignore. 


Local , Git , Server

Local doesn't directly connect to server right. 
Local connects to Git. Server fetches the code from git. The Server will host the app to enduser. 

All the commands that we write in local, will also be in server. 
If we do npm install on server, this we can install our node modules again. 
So the copy of node modules in the local and server will look exactly the same. but they are not the same. 
It will have its own different dist folder. So we do not have to put parcel-cache or dist in git.

So will add these in git ignore/node_modules
.parcel-cache
/dist
/node_modules


If we use create-react , it will automatically do everything for you. 

Lets make our app compatible with older version of browser. 
There is something known as browser list 
If we go to node modules, we can see browser list. 

Browser list is a npm package. It needs some configuration. 
Check the website. You should tell your project, what all browsers your app needs supported in. 
In package.json you will add 

  "browserslist":{
    "last 2 chrome version",
    "last 2 firefox version"
  }

  Whatever the last 2 chrome versions are there, our app will be compatible for that. 
It might or might not work on other versions of browser, but it will definitely work on the mentioned version of broswers in the browser list. Checkout the browserlist website. What if we created it for all browser with all version, It will create a bundle and the code will add up."last 2 version" willl cover all the browser's last 2 version.  
We can configure depending on devices, area, etc. 

Parcel is doing all these things for us. It does everything on its own with the help of all the libraries. 

Now we have created a whole create react app. 

