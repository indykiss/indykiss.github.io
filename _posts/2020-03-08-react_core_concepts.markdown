---
layout: post
title:      "React core concepts"
date:       2020-03-08 21:19:47 -0400
permalink:  react_core_concepts
---


For the past ~2 months, I've been busy studying data structures and algorithms, building out an application for a code assessment, relearning SQL and generally interviewing. 

I've been using my github to keep track of my personal progress in the pursuit of coding knowledge. I tend to review the same concept over and over again until it's basically second nature, which can be nice usually, but tends to be a slightly detrimental habit when there's a laundry list of things to master. **cough cough *looking at you stacks, queues, heaps, tries, vectors, mergesort, quicksort, bubblesort.*** 

I've found using a repo useful in auditing the leetcodes I've done and saying to myself, "Ok, you've done like 12 linked lists algos and only two graphs. Go do some graphs." 

My random-assortment-of-algos can be found here if interested: [https://github.com/indykiss/DataStructures-Algos ](https://github.com/indykiss/DataStructures-Algos)

Generally, I like to pull particularly difficult (difficult for me, at least) algos out to blog about. 

But today I'm going to focus on some React core concepts. I love the things that React can do, but unfortunately I've not had the pleasure of deep diving into it. I've only used React in one of my applications thus far ([Data-scape](http://https://github.com/indykiss/Data-scape)), but will admit its implementation needs work. 

So, time to bring it back to the basics! 


## What's React? Why is React used? 

React is a JS library built by Facebook. It's used for creating seamless, user friendly UIs. React is a great framework for creating single page applications and for making interactive pages without needing to refresh the page. 

It's one of the most popular frameworks in the industry because of its easy to build interactivity, its independent components that controls their own state, and its virtual dom functionality. 


## Important React factoids

### JSX

React uses JSX, which lets us incorporate JS in markup (basically mixes html and JS in one). This can be seen in the render() section of the component, which is what the user uses on the page. Render() is the lifecycle method that renders the component in the browser. 

### Create-react-app

Create-react-app is a great tool for building a basic app. Npm start starts up the built in dev server. You need to have node.js great for npm, which is needed for create-react-app. 

The structure of create-react-app:
- Package.json, which lists info about the app. Dependencies and packages we're using. React, react-dom (loads the components within the browser), react-scripts (lets our dev server compile the application). 
- Public: Index.html. This is the one physical single page that has all the react components. Specifically in the ` <div id = "root"> </div>`.
- Src: The source folder. Contains the Index.js. This is the entry point of the React library. This connects the App component with the index.html root.
- App.js is the App component. Here we will import all of our custom components and add it into render. 

### State and props

Each component handles its own state, but usually best for very simple apps to just have App component manage state that all components can access. 

When we have the overall App component managing state, and we want to pass state down to the ToDo list components, we pass it down as a prop.

A very basic React component with props looks like:

```
// App.js
Class App extends React.Component {
    
  state = {
    title: 'I am a dog', 
    body: 'This is my dog story',
	friends: [
		 { id: 1, 
		   name: Spot }, 
			 goodboy: false;
		 { id: 2,
		  name: Sparky,
			goodboy: false}
	]
  }
		
  render() {
    return(
      <div>
       <h3> {this.state.title} </h3>
       <p> {this.state.body} </p>
			 <Bojangles friends={this.state.friends}>
      </div>
    )
  }
}

// Bojangles.js component in a Component folder
import stuff 

Class Bojangles extends Component {

  render() {
	  return(
		<div>
		  <h2> My friends are: (this.props.friends.map((friend) => (
			     {friend.name}
			  )</h2>
		</div>
		)
	}
}

```
Note: Each prop should have a key passed in that's the ID number. You'll see an error about it. Vaguely like: 
``` <Friend key = {friend.id} name = {friend}> ```


### React hook 

Hooks are functions that let you “hook into” React state and lifecycle features from function components. Hooks don’t work inside classes — they let you use React without classes. 

Hooks let us easily manipulate the state of our functional component without needing to convert them into class components.


### Functional vs class based components 

A functional component is just a plain JavaScript function which accepts props as an argument and returns a React element. Can't use setState here.

A class component requires you to extend from React.Component to create a render function which returns a React element. 

Use functional components when the component doesn't need to handle its own state. Otherwise, class components have much more functionality. 


## More questions

### What is a virtual DOM? Why is it called a virtual DOM? 

The virtual DOM (VDOM) is a programming concept where an **ideal**, or “virtual”, representation of a UI is kept in memory and synced with the “real” DOM by a library such as ReactDOM. This process is called reconciliation.

In React, for every DOM object, there is a corresponding “virtual DOM object.” A virtual DOM object is a representation of a DOM object, like a lightweight copy. A virtual DOM object has the same properties as a real DOM object, but it lacks the real thing's power to directly change what's on the screen.

A virtual DOM lets us update only what's needed, not the entire page. 


### What is React's lifecycle? 

The React lifecycle methods are the series of events that happen from the birth of a React component to its death.

Essentially: [http://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/ ](http://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/)

**Mounting** – Birth of component: Render() <br/>
**Update** – Growth of component: Render() / componentDidMount() / componentDidUpdate() <br/>
**Unmount** – Death of component: componentWillUnmount()


**Render** is a pure function. Pure functions are those that do not have any side-effects and will always return the same output when the same inputs are passed. 

**componentDidMount():** Called as soon as the component is mounted and ready. This is a good place to initiate API calls, if you need to load data. Can set state here cautiously.

**componentDidUpdate():**  Common use case is updating the DOM in response to prop or state changes. Can set state here cautiously.

**componentWillUnmount():** Called just before the component is unmounted and destroyed. If there are any cleanup actions that you would need to do, this is the spot.



### How can you debug a React component? 

React developer tools for chrome is an add in that lets us debug easily. We can use it within the browser to see the component structure, state, props.  


### What's the difference between a React component and a container? 

A React component is essentailly a chunk of code that accomplishes a single responsibilty. 

For example, if we're building a todo app, we would have search as one component, the todo list as one component, each todo item as another, and adding a new todo as a last component. 

A container is basically a component that's connected to a Redux store. 


### What's state and what is Redux? 

State is an object that determines how a component renders and behaves. Each component controls its own state. 

However, when we want to have an application-wide state management system, we use something like Redux. 

Redux is a JS library that helps us manage the data you display and how the app responds to user actions.


### What is an event handler in React? 

One great thing about React is the ability to add event handlers to take in input from the user. onChange, onSubmit, onClick are examples. 

For example:


``` 
// GoodBoy component
import stuff

Class GoodBoy extends React.Component {

// Always use an arrow function for our custom functions because it allows us to see props without binding
  sayYes = () =>{
    console.log("Yes, a very good boy");
  }


  render() {
    return(
	    <h3>
	    <p>Is this dog a good boy?</p>
	     <input type = "checkbox" onChange = {this.sayYes} />
	    </h3>
	  )
  }

}

export default GoodBoy;
```

We need to remember to climb the ladder of props for our components. 
For example, if there's: App => Bojangles => GoodBoy.

We need to pass the props that are created on GoodBoy to Bojangles before App has access to that data. 


Destructuring the props can make passing data up the ladder easier. That's the const {id, name} = this.props.friends part

To climb the props ladder, we'll add in GoodBoy:

```
... 
render() {
const {id, name} = this.props.friends

 return(
  ... 
  <input type = "checkbox" onChange = {this.props.sayYes.bind(this, id)}>
  ...
 )
}
...
```

So we can add in Bojangles:

```
...
render() {
 return(
  ...
  <GoodBoy key ={friend.id} friend = {friend} sayYes = {this.props.sayYes}>
 )
}
...
```

And in App.js:
```
... 
sayYes = (id) => {
 console.log("Yes, very much a good boy friend.")
 
 this.setState( { friends: this.state.friends.map(friend => {
   if(friend.id === id) {
	   friend.goodboy = !friend.goodboy
	 } else {
	 return friend}
 }) });
}
... 
```


### Remember that React is just the V part of the MVC model of an application. 
### React needs to be connected to a backend for it to work. We can make HTTP requests using something like Axios, to fetch data. 

<br/>
Thanks for reading, <br/>
Indy

