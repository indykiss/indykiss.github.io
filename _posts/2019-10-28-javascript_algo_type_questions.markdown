---
layout: post
title:      "JavaScript algo type questions"
date:       2019-10-28 10:53:09 -0400
permalink:  javascript_algo_type_questions
---


For the past few weeks, I've been going over basic interview questions, ranging from core CS concepts (the basics) to CS theories and principles, to JavaScript conceptual questions (again, just the basics). 

Now I'll be going into a series that extends past these basics and goes a little deeper into actual strategies to answering algo-type questions. 

I'm going to start with 2-3 easy algos a week and ramp up to harder one; from array manipulationg to recursive spiral matrices (which is apparently an easier algo, but for me, for right now, this is a tougher one). 

<br>

*How to add to the start and to the end of an array?*
```
myArr = [a,b,c,d]
myNewArr = ["start", ...myArr, "end"]
```
* This is the ES6 format. If can't use ES6 for whatever reason, then do .push("end") or .unshift("start"). 


*FizzBuzz. Write a program that prints out 1-100. For every mutiple of 3, print out Fizz. For every multiple of 5, print out Buzz. For every multiple of 3 and 5, print out FizzBuzz.*

```
function fizzBuzz(n) {
  for (var num = 1; num <= n; num++) {
    if(num%3 === 0 && num%5 === 0) {
      console.log("FizzBuzz")
    }
      else if(num%3 === 0){
        console.log("Fizz")
      }
        else if(num%5 === 0){
          console.log("Buzz")
        }
      else {
        console.log(num)
      }
  }
}

fizzBuzz(16);
```


*Fibonacci Series. A series of numbers in which each number is the sum of the proceeding two numbers. The Fibonacci series goes like 1, 1, 2, 3, 5, 8 etc...  Write some code that continues this series.*
* Since we are relying on the previous sum of the past 2 results, we are going to use a very simple version of recursion. It's important to keeep in mind for recursive solutions, you need to start off with a base case for when the recursion ends. We don't want an infinite loop! 

```
function fib(n) {

if (n <2) {
return n;
}

return fib(n-1) + fib(n-2);
}
```



Thanks for reading!<br>
Indy 


P.S.- Check out my new website! [https://indirak.wixsite.com/indycode](http://) <br>
Domain name still pending. Probably going to do a indy.info or something short and easy to type :) TBD
