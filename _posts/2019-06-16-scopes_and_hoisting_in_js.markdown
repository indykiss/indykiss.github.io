---
layout: post
title:      "Scopes and Hoisting in JS"
date:       2019-06-16 13:54:21 -0400
permalink:  scopes_and_hoisting_in_js
---

This blog is a quick how-to guide for scopes and hoisting in JS.

Reminders:

- Since JS is a compilation language, it's good to remember that it has two phases; compilation and execution. During compliation, essentially the global and local scopes register what's going on in the function. During execution, the system will do what the code is asking for (pending any bugs). 
- There are three types of variable declarations: *let*, *const* and *var*. All three are treated differently in JS.  Let and const are ES6 syntaxes.



### What is scope?

Scope is essentially the spaces where code and data can be used. 

Let's look at an example.

```

var persian = "Babylon"

function kitty() {
   let maineCoon = "Portland"
   const scottishFold = "Edinburgh"
   var russianBlue = "Moscow"

 if (true) {
    let maineCoon = "PORTLAND" 
    const scottishFold = "EDINBURGH"
    var russianBlue = "MOSCOW"
 }

   console.log(maineCoon)
   console.log(scottishFold) 
   console.log(russianBlue)
}

kitty() 

```

In the above example, persian is a global variable, while mainCoon, scottishFold and russianBlue are all local because they're declared within a function. Try not to use global variables often. As your code gets more complicated, you may need to use the variable name "persian" again in local scope. But since we have "persian" in the global scope, that will complicate things. 

Now let's focus on the local variables.

See how we've declared the three local variables again within the if block? Now what happens when we run kitty()? 

The differences between *let*, *const* and *var* come into play. 

Const can't be reassigned. So scottishFold is going to stay "Edinburgh" no matter what we do to it. However, *let* and *var* can be reassigned. 

In this case, russianBlue will be reassigned to "MOSCOW". Var is mutable, so changing its value in the if block will change its value throughout the function.

maineCoon will be "Portland" because we are console logging at the same level/scope as the original declaration. However, if we console logged maineCoon in that inner if block, like: 

```

function kitty() {

   let maineCoon = "Portland"

   if (true) {
      let maineCoon = "PORTLAND" 
      console.log(maineCoon)
    }
}

kitty() 

```

Then maineCoon will be "PORTLAND",  because it keeps the value of that scope (the if block scope).

So to summarize:
- *Let* is flexible; it takes the value of the scope it is in. Try to use *let* the most often because of this flexibilty. 
- *Const* is constant; it will only be the value you declare the first time around. 
- *Var* is a bit of a loose cannon; its value can be reassigned and doesn't necessarily stay within the desired scope. 



### What is hoisting? 

Let's tackle hoisting for variables first. We have this function:

```

function doggyCute() {
   console.log("Spot is ", puppy)
 
   var puppy = "8 weeks old"
 } 
 
 doggyCute() 
 
 
```

During compilation, the existence of puppy as a variable gets hoisted to the top of its scope because we're using *var*, but the value, "8 weeks old" does not get lifted up.

So that means doggyCute() will be undefined; it recognizes that puppy exists (so it won't yield an error) but since the value "8 weeks old" didn't get hoisted, we didn't get "Spot is 8 weeks old."

Keep in mind that *let* and *const* are treated differently. They are initialized differently so the existence of their variables aren't hoisted the same way.


Now let's look at functions.

Function declarations (and their values!) are hoisted, but not function expresses. 

What's the difference you might ask? 


Function declaration (yes hoisted):
```

function doggyCute() {
   console.log("Spot is ", puppy())
 
    function puppy() {
	      console.log(" super adorable.") 
		}
 } 
 
doggyCute()
```

... yielding "Spot is super adorable."


Function expression (not hoisted): 
```
function doggyCute() {
 console.log("Spot is ", puppy)
 
 var puppy =  function pupPup() {
	    console.log(" super adorable.")
	 }
 } 
 
doggyCute()

```

... yielding an error. 



Generally, best practice in coding is to declare all the necessary variables at the top of a function to mimic what the compliation stage is going to do. 




Thanks for reading!

Indy
