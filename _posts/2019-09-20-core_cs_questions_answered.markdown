---
layout: post
title:      "Core CS questions answered"
date:       2019-09-20 15:00:53 -0400
permalink:  core_cs_questions_answered
---



*SOLID principles of programming: Made to make systems easier to maintain and understand. 
*

1. S is for single responsibility principle. Each segment of code (function, module, method, etc) is only responsibile for 1 task within the system. Helps with debugging. 
2. O is for open/ closed principle. Code should be open for extension but not for modification. 
3. L is for the Liskov substitution principle. Objects in a program should be replaceable by instances of their subtyps without altering their correctness. 
4. I is for interface segration principle. No client should be forced to rely on methods it does not use. 
5. D is for dependence inversion principle. Abstractions are good. High level modules should not depend on low level modules. Both need to depend on abstractions.  


*OOPS concepts: Main ideas behind Java's object oriented programming. Good to know for object orientation in general. 
*

1. Abstraction: Vague.ifying. We use blueprints to hide details and only show relevant data. 
2. Encapsulation. We hide data implementation by restricting access to public methods. 
3. Inheritance. Anything the parent class has, the child class will also have. 
4. Polymorphism. Ability of an object to take on multiple forms. 


*What is an interface? And what is the difference between an interface and an abstract class? (Again, kinda Java.ie but good to know). *

*  Essentially, an interface is an set of abstract methods that can't be implemented (meaning, by itself, you can't call on its methods to make an object or like do anything). Therefore, it can't be initiated. 
An abstract class can have instance methods that can implement a default behavior. 



<br> </br>

**Javascript conceptual Qs
**


*Like what even is Javascript? 
*

* JS is a client-side and server-side object orientated language, that's understood by web browsers. It's data types are number, string, boolean, object and undefined. 
* 

*Name some core JS built in functions.
*

* .String( ) = makes a thing a string
* .Number( ) = makes a thing a number
* .length( ) = if argument is a string, it tells us how many characters there are in it
* str.indexOf(thisThing) = searches through a string to find the index of thisThing 
* str.lastIndexOf(thisThing) = searches through str to find the last instance of thisThing. 
* For both of the above IF thisThing isn't even in there; the function will return -1. Also a second parameter is taken to say where we want to start searching 
* If we want to use RegEx, then .seach( ) is best but no second parameter allowed 
* .slice( ) extracts a part of a string and returns the extracted part in a new string
* 



*What are the JS value properties? *

* Infinity
* NaN
* undefined
* null 

*What are the JS data types? 
*

* Primitive (where typeof works): number, string, boolean, undefined 
* Complex: function, object. Arrays, hashes and null are all objects. myFunc( ){ } is a function.



*What is JSON? And what are some JSON methods? 
*

* Javascript object notation is a readable format for structuring data that gets passed from server to the web app. 
* JS has two main methods to manipulate JSON data. There's .parse( ) that is used to parse a JSON string and returns an object. There's .stringify( ) that does the opposite; takes an object and converts it into a JSON string. 
* So, we send data to the server using .stringify( ) but receive data that we want to use with .parse( ). 


*What are some JS global functions/ function properties? 
*

* .eval( )  = Enables code that's in a string. Essentially console.log(eval("2 + 2")) = 4. Normally, that stuff is just "2+2"
* .isNan( ) = Is this NaN or not?
* .isFinite( ) = To be infinity or not to be infinity? 
* .parseFloat( ) = Splits an argument (converting it to a string) and returns a number with a decimal (hence the float thing)


```
function circumference(r) {
  return parseFloat(r) * 2.0 * Math.PI;
}
console.log(circumference(4.567));
// expected output: 28.695307297889173
```


* .parseInt(string, radix ) = Splits a string argument and returns an integer based on a base 

```
function roughScale(x, base) {
var parsed = parseInt(x, base);
if (isNaN(parsed)) { return 0 }
return parsed * 100;
}
console.log(roughScale(' 0xF', 16));
// expected output: 1500
console.log(roughScale('321', 2));
// expected output: 0
```


* [etc... other things that I've never used]
* 



<br> </br>

**JavaScript algo type questions**

*How to add to the start and to the end of an array? 
*

```
myArr = [a,b,c,d]
myNewArr = ["start", ...myArr, "end"]
```

This is the ES6 format. If can't use, then do .push("end") or .unshift("start"). 



*FizzBuzz. Write a program that prints out 1-100. For every mutiple of 3, print out Fizz. For every multiple of 5, print out Buzz. For every multiple of 3 and 5, print out FizzBuzz. 
*
<br></br>

```
Insert solution here
```


*Fibonacci Series. A series of numbers in which each number is the sum of the proceeding two numbers. The Fibonacci series goes like 1, 1, 2, 3, 5, 8 etc...  Write some code that continues this series. 
*

* Since we are relying on the previous sum of the past 2 results, we are going to use recursion. 


```
function fib(n) {

if (n <2) {
return n;
}

return fib(n-1) + fib(n-2);
}
```


<br></br>

Work in progress! Blog will be updated as I learn new things and learn about what things I need to learn about. 


Thanks for reading, </br>
Indy






