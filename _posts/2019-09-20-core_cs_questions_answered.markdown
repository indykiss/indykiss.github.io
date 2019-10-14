---
layout: post
title:      "Core CS questions answered"
date:       2019-09-20 15:00:53 -0400
permalink:  core_cs_questions_answered
---


As I deepen my basic knowledge of JavaScript and all things code, I'm going to deep dive into a Q & A series of blogs for core computer science concepts, theories and principles, JS concepts and algorithmic strategies. 

This first blog will be a bit of a board of ideas that I'll flesh out more as the weeks go by. 

Excited to learn more about the theory behind the code! 



**Basics**

*What is a data structure?*
* A data structure is a collection of data values, the relationships among them, and the functions or operations that can be applied to the data. In Javascript, the primitive data types are numbers, strings, boolean, undefined and null. Objects like functions and arrays are non-primitive structures. Main difference is that primitive data structures are immutable while non-primitices are mutable. 
 
*Why wrap code in functions?*
* Wrapping code in functions allows for easy reference later on and allows us to keep code ensapulated, which is important to keep scope organized. 
 
*What is a hash table?*
* A hash table is a dictionary type data structure that maps keys to values. It allows people to look up a value based off its key. 

*What is a stack?* 
* A stack is a collection of elements that is based on a last in, last out policy. There are two principle operations; push, which adds an element, and pop, which takes off an element. 

*What's the difference between a stack and an array?*
* An array is a collection of similar data type, identified by index, while a stack is a linear data structure that represents sequential collection of element in fixed order. The main difference is access. You can access any element in an array by using indices. You can't access all the elements in a stack; you can only get the element at the top using push and pop. 

*What is a queue*
* A queue is a data linear data structure that follows a particular order in which the operations are performed. Essentially, like a queue of people trying to buy stuff; first in, first out. 

*What's a priority queue?*
* A queue, which instead of operating on a first come, first out order, operates on a priority basis. 

*What is a heap?*
* A tree-based data structure that effeciently implements a priority queue, first-in/first-out. 

*What is a min and a max heap?*
* A max heap is when, in a heap, the parent nodes are higher than its children nodes. A min heap is the opposite, where children nodes are higher than its parent nodes. 

*What is the difference between a heap and priority queue?*
* Heaps are used to implement priority queues. A heap's shape as well as its order (min vs max) are its two main properties. 





<br> </br><br></br>

**Javascript conceptual Qs**


*What even is Javascript?*
* JS is a client-side and server-side object orientated language, that's understood by web browsers. It's data types are number, string, boolean, object and undefined. * 

*Name some core JS built in functions. Aka JS string operations.*
* .toString( ) = makes a thing a string
* .toNumber( ) = makes a thing a number
* .length( ) = if argument is a string, it tells us how many characters there are in it
* str.indexOf(thisThing) = searches through a string to find the index of thisThing 
* str.lastIndexOf(thisThing) = searches through str to find the last instance of thisThing. 
* For both of the above IF thisThing isn't even in there; the function will return -1. Also a second parameter is taken to say where we want to start searching 
* If we want to use RegEx, then .search( ) is best but no second parameter allowed 
* .slice(start index, opt. second index not inclusive) extracts a part of a string and returns the extracted part in a new string

*What is "this" in JS?* 
This refers to the object that is currently being called

*What are the JS value properties?*
* Infinity
* NaN
* undefined
* null 

*What are the JS data types?*
* Primitive (where typeof works): number, string, boolean, undefined 
* Complex: function, object. Arrays, hashes and null are all objects. myFunc( ){ } is a function.


*What is JSON? And what are some JSON methods?*
* Javascript object notation is a readable format for structuring data that gets passed from server to the web app. 
* JS has two main methods to manipulate JSON data. There's .parse( ) that is used to parse a JSON string and returns an object. There's .stringify( ) that does the opposite; takes an object and converts it into a JSON string. 
* So, we send data to the server using .stringify( ) but receive data that we want to use with .parse( ). 

*What are some SQL basics?* 
* Select, where, limit (top 5 for ex), order by (asc/ dec), group by, and, or, min, max, avg, sum, count. Joins combine rows from two or more tables


*What are the enumerable operators in Javascript?*
* map(), .each(), .find(), .search() and maybe .reduce()

*How can you find the sum of the elements in an array? / The smallest element / the largest element?*
* Math.min(rr), Math.max(arr), arr.reduce()


*In JS, what's the diffference between const, let and var?*
* The scope is the main difference. Var is globally scoped while let and const are block scoped.

*What is the difference between double and triple equals in JS?*
* Triple equal checks for strict equality, checking type and value. Double equals checks for loose equality, so just value not type.  

*What are some JS global functions/ function properties?*
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




<br></br><br></br>

**JavaScript algo type questions**<br></br>

*How to add to the start and to the end of an array?*
```
myArr = [a,b,c,d]
myNewArr = ["start", ...myArr, "end"]
```
* This is the ES6 format. If can't use, then do .push("end") or .unshift("start"). 



*FizzBuzz. Write a program that prints out 1-100. For every mutiple of 3, print out Fizz. For every multiple of 5, print out Buzz. For every multiple of 3 and 5, print out FizzBuzz.*

```
Insert solution here
```


*Fibonacci Series. A series of numbers in which each number is the sum of the proceeding two numbers. The Fibonacci series goes like 1, 1, 2, 3, 5, 8 etc...  Write some code that continues this series.*
* Since we are relying on the previous sum of the past 2 results, we are going to use recursion. 
```
function fib(n) {

if (n <2) {
return n;
}

return fib(n-1) + fib(n-2);
}
```



</br>

Work in progress! 


Thanks for reading, </br>
Indy






