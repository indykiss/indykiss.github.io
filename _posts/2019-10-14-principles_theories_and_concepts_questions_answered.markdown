---
layout: post
title:      "Principles, theories and concepts questions answered"
date:       2019-10-14 13:47:12 -0400
permalink:  principles_theories_and_concepts_questions_answered
---


As I deepen my basic knowledge of JavaScript and all things code, I’m going to deep dive into a Q & A series of blogs for core computer science concepts, theories and principles, JS concepts and algorithmic strategies. This is my second week of blogging this series. 

For this week's blog about common interview questions answered, I'm going to look at a few of the common theories about programming.


<br></br>
*What is object oriented programming?*
* Object oriented programming focuses on the usage of objects to represent data and methods. Object oriented programming implements real-world entities like inheritance, encapsulation, polymorphism and abstraction using classes and objects. The main goal is to bind data and the functions that operate on them so that no other part of the code can access this data except that function. 
* Inheritance is the concept that child classes inherit the properties that their parent classes have. Encapsulation is the thought that data should be wrapped in a container. Polymorphism is the practice of writing a single function that can handle different data types. Abstraction is the practice of hiding the implementation details and only showing functionality to the users. 

*What is functional programming?*
* Functional programing is a programming paradigm using pure functions, which avoids side-effects from global variables, mutable data, and share state. Functional code tends to be concise, predictable and easier to test than object oriented code.

*Pros and cons of OOP vs functional programming?*
* In OOP, its easy to understand basic objects and easy to interpret the meaning of method calls, but since OOP depends on shared state, sometimes by lumping together objects with behaviors on the same entity, that can lead to undesired behavior. 
* In FP, since shared state and side-effects are avoided, there's fewer bugs and the code is simpler. But because of its simplicity, there's less readability because the code becomes more terse and less conrete. 

*What is asynchronous programming?*
* In asynchronous programming, multiple things happen at the same time. So when a user starts an action, the program continues to run; an example being when a user clicks a button on a UI and the page is still rendered while the data requested gets fetched, which is helpful for performance.

*SOLID principles of programming: Made to make systems easier to maintain and understand.*
1. S is for single responsibility principle. Each segment of code (function, module, method, etc) is only responsibile for 1 task within the system. Helps with debugging. 
2. O is for open/ closed principle. Code should be open for extension but not for modification. 
3. L is for the Liskov substitution principle. Objects in a program should be replaceable by instances of their subtyps without altering their correctness. 
4. I is for interface segration principle. No client should be forced to rely on methods it does not use. 
5. D is for dependence inversion principle. Abstractions are good. High level modules should not depend on low level modules. Both need to depend on abstractions.  

*Object oriented programming concepts?*
1. Abstraction: Vague.ifying. We use blueprints to hide details and only show relevant data. 
2. Encapsulation. We hide data implementation by restricting access to public methods. 
3. Inheritance. Anything the parent class has, the child class will also have. 
4. Polymorphism. Ability of an object to take on multiple forms. 
5. Class - A collection of method and variables
6. Object - An instance of a class. 

*Can you name two programming paradigms that are important for JavaScript?*
* One would be prototypal inheritance, which is basically objects inheriting from other objects. 
* Another one would be functional programming, essentially the ability to keep functions pure by eliminating side effects and ensuring predictable outputs given the same inputs. 

*Difference between classical inheritance and prototypal inheritance?*
* Classical inheritance is when instances inherit from classes and create sub-class hierarchies. In practice, classical inheritance is using the 'new' keyword. 
* Prototypal inheritance is when instances directly inherit from other objects, which is simpler and more flexible than classical inheritance. 


*What is an interface? And what is the difference between an interface and an abstract class? (Java-based)*

*  Essentially, an interface is an set of abstract methods that can't be implemented (meaning, by itself, you can't call on its methods to make an object or like do anything). Therefore, it can't be initiated. 
* An abstract class can have instance methods that can implement a default behavior. 


<br></br>

Thanks for reading,
<br></br>
Indy
