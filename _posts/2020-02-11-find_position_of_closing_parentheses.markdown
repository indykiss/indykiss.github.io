---
layout: post
title:      "Find position of closing parentheses"
date:       2020-02-11 15:52:44 +0000
permalink:  find_position_of_closing_parentheses
---



Find the position of the matching closing parenthesis in a sentence where we know the index of the opening 
parenthesis. 


###### Strategy: 
1. We loop through the sentence. 
2. As we loop, we increment a counter as we see "C" in openNestedParens. 
3. As we find a closing ")" we decrement the openNestedParens. 
4. Once we find a closing ")" and the counter is at 0, then we are done and can return that position. 


###### Lesson Learned: 
For "parsing" algos, use a stack to track  brackets/ parentheses/ phrases/ etc that are "open" as we go. 
This lets us store the number of items, not the items, which lets us use a stack with just using an integer. 
Which is really great for space and time efficiency. 
*/


```

function getClosingParen(sentence, openingParenIndex) {
  let openNestedParens = 0;
  
  // Loop through sentence
  for(let i = openingParenIndex + 1; i < sentence.length; i++) {
    const char = sentence[i];
    // If char is an open paren, increment
    if(char === "(") {
      openNestedParens++;
    }
    // If it's closing paren AND there's unpaired opens
      // decrement the counter
    if(char === ")" && openNestedParens > 0) {
      openNestedParens--;
    }
    // If it's a closing paren AND no unpaired opens 
      // Return position
    if(char === ")" && openNestedParens === 0) {
      return i;
    }
  }
  throw new Error("No closing parenthesis")
}

/* 
O(n) time because looping, which is worst case and also the minimum because we have to look at everything at least once
O(1) space because we only have a constant to store
*/
 
  
```


Thanks for reading!<br>
Indy

