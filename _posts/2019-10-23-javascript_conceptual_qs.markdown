---
layout: post
title:      "JavaScript conceptual Qs"
date:       2019-10-23 19:57:47 +0000
permalink:  javascript_conceptual_qs
---


For this week’s blog about common interview questions answered, I’m going to look at a few of the common conceptual questions about JavaScript specifically. 


</br>

*What even is Javascript?*
* JS is a client-side and server-side object orientated language, that's understood by web browsers. It's data types are number, string, boolean, object and undefined. * 

</br>
*Name some core JS built in functions. Aka JS string operations.*
* .toString( ) = makes a thing a string
* .toNumber( ) = makes a thing a number
* .length( ) = if argument is a string, it tells us how many characters there are in it
* str.indexOf(thisThing) = searches through a string to find the index of thisThing 
* str.lastIndexOf(thisThing) = searches through str to find the last instance of thisThing. 
* For both of the above IF thisThing isn't even in there; the function will return -1. Also a second parameter is taken to say where we want to start searching 
* If we want to use RegEx, then .search( ) is best but no second parameter allowed 
* .slice(start index, opt. second index not inclusive) extracts a part of a string and returns the extracted part in a new string

</br>
*What is "this" in JS?* 
* This refers to the object that is currently being called

</br>
*What are the JS value properties?*
* Infinity
* NaN
* undefined
* null 

</br>
*What are the JS data types?*
* Primitive (where typeof works): number, string, boolean, undefined 
* Complex: function, object. Arrays, hashes and null are all objects. myFunc( ){ } is a function.

</br>
*What is JSON? And what are some JSON methods?*
* Javascript object notation is a readable format for structuring data that gets passed from server to the web app. 
* JS has two main methods to manipulate JSON data. There's .parse( ) that is used to parse a JSON string and returns an object. There's .stringify( ) that does the opposite; takes an object and converts it into a JSON string. 
* So, we send data to the server using .stringify( ) but receive data that we want to use with .parse( ). 

</br>
*What are some SQL basics?* 
* Select, where, limit (top 5 for ex), order by (asc/ dec), group by, and, or, min, max, avg, sum, count. Joins combine rows from two or more tables

</br>
*What are the enumerable operators in Javascript?*
* map(), .each(), .find(), .search() and maybe .reduce()

</br>
*How can you find the sum of the elements in an array? / The smallest element / the largest element?*
* Math.min(rr), Math.max(arr), arr.reduce()

</br>
*In JS, what's the diffference between const, let and var?*
* The scope is the main difference. Var is globally scoped while let and const are block scoped.

</br>
*What is the difference between double and triple equals in JS?*
* Triple equal checks for strict equality, checking type and value. Double equals checks for loose equality, so just value not type.  

</br>
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

</br>

Thanks for reading! 
</br>
Indy
