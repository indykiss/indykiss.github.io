---
layout: post
title:      "JavaScript Algos Pt. 3"
date:       2019-11-22 17:15:27 -0500
permalink:  javascript_algos_pt_3
---


I had an interview this week that asked me a really interesting algo. I'm going to anonymize the instructions a bit to make sure any confidentiality issues are kept in check. 

The first algo was a warm up. The second was a more complicated hash-related algo with a couple of fun loops. 


### Reverse a string without using .reverse()

The goal of this warm up algo is to reverse a string without using the array built-in method .reverse(). To do that, we would need to do an iteration through the string starting from the end of the string. The below is a nicer way to do this than my initial approach. I had made the string into an array with split, then joined at the end; very unnecessary manipulation there. 

```

// reverse("abc") ==> "cba"

function reverse(str) {

     let newStr = "";

     for(var i = str.length -1; i >= 0; i--) {
		      newStr += str[i]
     }

     return newStr;

}

reverse("abc")
```

### More complicated algo! Finding the highest average gambler. 

We are given an input of nested arrays. Each nested array is a name and price (the amount that a person has gambled in a day). Gamblers are included in the input multiple times. Find the person who has on average gambled the most money. 

This is the solution that I found during the interview: 

```

// highestAvg([["John", 50], ["Max", 20], ["John", 50]]); ==> John


function highestAvg(arr) {
  let newHash = {}; 
  let max = 0;
  let maxPerson = '';

  for(var i = 0; i <= arr.length - 1; i++) {
    let gName = arr[i][0]
    let costs = arr[i][1]
    if(newHash[gName]) {
      newHash[gName].push(costs);
    } else {
      newHash[gName] = [costs];
    }
  }

  for(let ele in newHash) {
    let newCost = newHash[ele]
    let sum = 0;

    for(var i = 0; i < newCost.length; i++) {
      sum += newCost[i];
    }
    
    let avg = sum/ newCost.length;
    
    if(avg > max) {
      maxPerson = ele;
      max = avg;
    }
  }
  return maxPerson;
}

highestAvg([["John", 50], ["Max", 20], ["John", 50]]);
```

<br>

This was my first in-person tech interview algo; it was so much fun! Looking forward to doing more of these. 

<br>

Thanks for reading,

Indy


