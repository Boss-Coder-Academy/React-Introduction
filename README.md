# React (Introduction)

### Agenda

1. **Introduction**
2. **Setup and Installation**:
3. **Create React App**
4. **Components in React**:
      + Functional Components
      + Class Components
5. **Props (Properties)**
6. **JSX (JavaScript XML)**
7. **State Management**
8. **Assignment**

---


## Introduction to React

React is a popular JavaScript library used for building user interfaces. It allows developers to create interactive and dynamic UI components, making it easier to develop complex web applications.

## Setup and Installation

### Installation

Follow the below steps to install Nodejs onto your system:

**Step 1**: Open https://nodejs.org/en/download/ and select your preferred OS under LTS.
 

![altImage](https://i.postimg.cc/KcpBGVkc/Whats-App-Image-2023-11-23-at-16-11-06.jpg)


**Step 2**: Open the setup wizard from the downloads of your system.


![altImage](https://i.postimg.cc/zGzk3WD8/Whats-App-Image-2023-11-23-at-16-12-38.jpg)



**Step 3**: Mark the checkbox and click next.

![altImage](https://i.postimg.cc/RV6By6xC/Whats-App-Image-2023-11-23-at-16-13-50.jpg)



**Step 4**: In the next window do not change everything just click next.

![altImage](https://i.postimg.cc/x8PtFPjp/Whats-App-Image-2023-11-23-at-16-15-01.jpg)


**Step 5**: Again, In the next window do not change everything just click next.


![altImage](https://i.postimg.cc/yxJ8LLTs/Whats-App-Image-2023-11-23-at-16-15-36.jpg)


**Step 6**: Click on install.

![altImage](https://i.postimg.cc/rFPP6QC7/Whats-App-Image-2023-11-23-at-16-17-00.jpg)


**After the previous step NodeJS will be installed on your system.**

![altImage](https://i.postimg.cc/Pqzyq4YX/Whats-App-Image-2023-11-23-at-16-18-30.jpg)


## Create React App

The easiest way to start a new React project is by using Create React App. This tool sets up a new React application with a predefined folder structure and development environment.

To create a new React app:

```bash
npx create-react-app my-react-app
cd my-react-app
npm start
```

This will initialize a new React project named `my-react-app` and start the development server.


## Components in React

### 1. Functional Components

Functional components are JavaScript functions that return React elements. They are also referred to as stateless components. In the context of React, they are "pure" functions; given the same input (props), they always return the same output (UI).

Example:

```javascript
import React from 'react';

function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

export default Greeting;


  );
}

export default FunctionalComponent;
```

**Explanation**:

+ **import React from 'react';**: Imports the React library.
+ **function Greeting(props) { ... }**: Declares a functional component named Greeting that accepts props as an argument.
+ **return `<h1>`Hello, {props.name}!`</h1>`;**: Returns JSX representing an `<h1>` element that greets the user with the name passed through props.
+ **export default Greeting;**: Exports the component to be used elsewhere in the application.



### 2. Class Components

Class components in React are JavaScript classes that extend React.Component. They are used for creating components with more features like state management, lifecycle methods, and more complex logic.

Example:

```javascript
import React, { Component } from 'react';

class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={() => this.setState({ count: this.state.count + 1 })}>
          Increment
        </button>
      </div>
    );
  }
}

export default Counter;


```
**Explanation**:

+ **import React, { Component } from 'react';**: Imports React and the Component class from the react library.
+ **class Counter extends Component { ... }**: Defines a class component named Counter that extends Component.
+ **constructor(props) { ... }**: Initializes the component's state with a count property set to 0.
+ **this.state = { count: 0 };**: Initializes the state object within the component's constructor.
+ **render() { ... }**: Defines the render method responsible for rendering the component's UI.
+ **`<p>`Count: {this.state.count}`</p>`**: Displays the current count value from the component's state.
+ **<button onClick={() => this.setState({ count: this.state.count + 1 })}>Increment</button>**: Renders a button that, when clicked, updates the count by calling setState, which triggers a re-render with the updated state.





## Props (Properties)

Props allow passing data from parent to child components. They are immutable and help create reusable components.

**Example**:

```javascript
// ParentComponent.js
import React from 'react';
import ChildComponent from './ChildComponent';

function ParentComponent() {
  return <ChildComponent name="John" />;
}

export default ParentComponent;

// ChildComponent.js
import React from 'react';

function ChildComponent(props) {
  return <p>Hello, {props.name}!</p>;
}

export default ChildComponent;
```
**Example Explanation**:

+ **ParentComponent.js**: This file imports the ChildComponent and renders it. The name prop with the value "John" is passed to ChildComponent.
+ **ChildComponent.js**: This file is a functional component named ChildComponent that receives props as its argument. It uses the name prop passed from the parent to display a greeting.


## JSX (JavaScript XML)

JSX stands for JavaScript XML. It's an extension to JavaScript syntax that allows developers to write HTML-like code within JavaScript. In React, JSX is commonly used to describe what the UI should look like.

**Example**:

```javascript
const element = <h1>Hello, JSX!</h1>;
```
**Example Explanation**:

+ **const element = `<h1>`Hello, JSX!`</h1>`;**: This line demonstrates the use of JSX, which allows HTML-like syntax within JavaScript. It creates a variable element representing an `<h1>` element with the text "Hello, JSX!".


## State Management

+ **State in Functional Components (useState hook)**

State allows components to manage their own data. In functional components, the `useState` hook is used to create and update state.

**Example**:

```javascript
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default Counter;
```



**Example Explanation**:

Counter Functional Component: This component manages its own state using the useState hook. It initializes a state variable count with an initial value of 0.
const [count, setCount] = useState(0);: useState(0) initializes count to 0, and setCount is a function used to update count.

+ `<p>`Count: {count}`</p>`: Displays the current count value stored in the count state variable.

+ <button onClick={() => setCount(count + 1)}>Increment</button>: Increments the count value by calling setCount when the button is clicked.


+ **Lifecycle Methods (Class Components)**: Class components have lifecycle methods that execute at different stages of a component's lifecycle, such as mounting, updating, and unmounting.

**Example**:

```javascript
import React, { Component } from 'react';

class LifecycleComponent extends Component {
  componentDidMount() {
    console.log('Component mounted');
  }

  componentWillUnmount() {
    console.log('Component will unmount');
  }

  render() {
    return <p>Component with lifecycle methods</p>;
  }
}

export default LifecycleComponent;
```



**Example Explanation**:

+ **LifecycleComponent Class Component**: This class component demonstrates lifecycle methods available in class components.
  
+ **componentDidMount() { ... }**: This method executes after the component is mounted (inserted into the DOM). It logs a message indicating that the component has been mounted.
  
+ **componentWillUnmount() { ... }**: This method executes just before the component is removed from the DOM. It logs a message indicating that the component will be unmounted.
  
+ **render() { ... }**: The render method is responsible for rendering the component's UI. It returns a simple <p> element.



## Assignment 

[Figma Link for assignments](https://shorturl.at/clP68)

**Figma Link**: 

```bash
[https://shorturl.at/clP68](https://www.figma.com/file/G63bpo5dcQTYk2VrjZSjZD/BCA-_Project_01--%2F-Coderflix-(OTT-Platform-)?type=design&node-id=0%3A1&mode=dev)
```

                           
**Task 1**: Design a Navigation Bar using React.

**Desired Output**:

![altImage](https://i.postimg.cc/gcNYhbmR/NavBar.jpg)

 
**Code**:

+ Make a ‘components’ folder inside the ‘src’ and create a file named header.js inside this components folder as shown:

![altImage](https://i.postimg.cc/pr74BZ0N/fva.jpg)

+ Also, create a ‘utils’ folder inside ‘src’ and a subfolder called ‘images’ inside utils and add all the required images in this folder.

![altImage](https://i.postimg.cc/BvqYHkqL/tyne.jpg)


+ Make sure that Tailwind is installed in this project. 
Now write the following code in different files as follows



**header.js**

```javascript

import React from 'react'
import logo from '../utils/images/logo3.png'
import userAvatar from  '../utils/images/account_logo.jpeg'
import bell from '../utils/images/bell_logo.png'
import dropdown from '../utils/images/dropdown_logo.png'


const header = () => {
    const toggleDropdown = () => {
      const dropdown = document.getElementById('dropdownContent');
      dropdown.classList.toggle('hidden');
    };
 
    return (
      <nav className="bg-gray-800">
        <div className="max-w-7xl mx-auto px-4">
          <div className="flex items-center justify-between h-16">
            {/* Left Side - Logo and Navigation Links */}
            <div className="flex items-center">
              <div className="flex-shrink-0">
                <img className='w-32' src={logo} alt="Logo" />
              </div>
              <div className="hidden md:block ml-4 text-sm">
                <a href="#" className="text-white px-2 py-2 hover:bg-gray-700 rounded">Home</a>
                <a href="#" className="text-white px-2 py-2 hover:bg-gray-700 rounded">TV Shows</a>
                <a href="#" className="text-white px-2 py-2 hover:bg-gray-700 rounded">Movies</a>
                <a href="#" className="text-white px-2 py-2 hover:bg-gray-700 rounded">New & Popular</a>
                <a href="#" className="text-white px-2 py-2 hover:bg-gray-700 rounded">My list</a>
                <a href="#" className="text-white px-2 py-2 hover:bg-gray-700 rounded">Browse By Language</a>
                {/* Other navigation links */}
              </div>
            </div>


           
 
            {/* Right Side - Account, Dropdown, Search */}
            <div className="flex items-center">


            {/* Search Bar */}
            <div className="ml-4">
                <input
                  type="text"
                  placeholder="Search..."
                  className="px-3 py-1 rounded bg-gray-700 text-white focus:outline-none"
                />
              </div>
             
              <div className='m-2 text-white'>
                Children
              </div>


              {/* Bell Image */}
              <div className="mr-2">
                <img className="w-10 h-10 " src={bell} alt="bell" />
              </div>


              {/* Account Image */}
              <div className="">
                <img className="w-8 h-8 " src={userAvatar} alt="User Avatar" />
              </div>


             
              {/* Dropdown */}
              <div className="ml-4 relative">
                <button
                  onClick={toggleDropdown}
                  className="text-white focus:outline-none"
                >
                  <img className='w-5 mt-3' src={dropdown}/>
                </button>
                {/* Dropdown Content */}
                <div
                  id="dropdownContent"
                  className="hidden absolute right-0 mt-2 bg-gray-700 text-white p-2 rounded shadow-lg"
                >
                  <a href="#" className="block hover:bg-gray-700 py-1">Settings</a>
                  <a href="#" className="block hover:bg-gray-700 py-1">Profile</a>
                  <a href="#" className="block hover:bg-gray-700 py-1">Logout</a>
                </div>
              </div>
 
              {/* Search Bar */}
             
            </div>
          </div>
        </div>
      </nav>
    );
  };
 
  export default header;

```



**App.js**

```javascript

import './App.css';
import Header from './components/header';
import MainContainer from './components/mainContainer';




function App() {
  return (
    <div>
      <Header/>
      <MainContainer />
    </div>
  );
}


export default App;

```


**Task 2**: Make a Video card:

**Desired Output**: 

![altImage](https://i.postimg.cc/s2gFsvGN/thw.jpg)



**Code**:

+ Under the ‘components’ folder, add a file and name it videoCard.js:
(header.js would already be present as it was created in the previous step)




+ Now add the following code inside the following files:

**videoCard.js**

```javascript
import React from 'react'
import cardImage from '../utils/images/card.jpeg'
import buttons from '../utils/images/buttons1.png'




const videoCard = () => {
    return (
        <div className="max-w-xs rounded overflow-hidden shadow-lg bg-gray-900 m-4">
          {/* Video Thumbnail */}
          <img
            className="w-full h-40 object-cover object-center"
            src={cardImage} /* Replace with your image URL */
            alt="Video Thumbnail"
          />
         
          {/* Video Information */}
          <div className="px-4 py-2 ">
            <div className="font-bold text-xl mb-2 text-white"><img src={buttons}/></div>
            <div className='flex'>
            <p className=" mr-2 text-green-500">97% Match</p>
            <p className="text-gray-300 text-base">2h 35m</p>
            </div>
            <div>
            <ol className='flex'>
                <li className="text-gray-300 text-base mr-2">Horror</li>
                <li className="text-gray-300 text-base mr-2">Adventure</li>
                <li className="text-gray-300 text-base">Mystery</li>
            </ol>
            </div>
          </div>
   
       
        </div>
      );
    };
export default videoCard
```



**App.js**

```javascript

import './App.css';
import Header from './components/header';
import videoCard from './components/videoCard';




function App() {
  return (
    <div>
      <videoCard />
    </div>
  );
}


export default App;

```



**Do not forget to add necessary images to the `images` folder inside `.utils`**




**Task 3**: Combine the two components in task 1 and task 2 and make a proper landing page.

**Desired Output**: 

![altImage](https://i.postimg.cc/s2qTqXYS/fevqf.jpg)


