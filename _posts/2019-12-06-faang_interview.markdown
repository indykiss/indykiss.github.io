---
layout: post
title:      "FAANG Interview "
date:       2019-12-06 17:44:21 +0000
permalink:  faang_interview
---


Ak! I feel both extremely unprepared but extremely lucky to be considered for a first round interview with this company. 

I've always been a huge proponent of their values. Their goal is to make the world a better, more connected place, which parallels my driving motivation to make a positive impact on the world. If I were to join this company, I would undoubtedly fulfill that goal while adding a unique, diverse voice to their chorus (but not physically singing, for everyone's sake haha).

First round interviews are usually behavioral, but this one might be half behavorial and half tech, so I'm going to do an easy leetcode algo in this post for some thought practice. Always could use more thought practice! 



### Verifying an Alien dictionary

In an alien language, surprisingly they also use english lowercase letters, but possibly in a different order. The order of the alphabet is some permutation of lowercase letters.

Given a sequence of words written in the alien language, and the order of the alphabet, return true if and only if the given words are sorted lexicographicaly in this alien language.

Input: words = ["hello","leetcode"], order = "hlabcdefgijkmnopqrstuvwxyz"
Output: true

Explanation: As 'h' comes before 'l' in this language, then the sequence is sorted.


```
var isAlienSorted = function(words, order) {
    // Words are the words we're looking at
    // Order is the alien alphabet
    
    let newArr = [...words]
    // Let's sort this replicated arr; best practice is to not alter original arr
        .sort((a, b) => {
    // We compare the first letter of the adjacent words in newArr to see if they are alphabetical
            for (let i = 0; i < a.length; i++) {
        // If there's a tie, we continue
                if (a[i] === b[i]) continue;
            // If the words aren't alphabetical we do maths to say its false
            // and vice versa. Goal is boolean so we do this:
                if (order.indexOf(a[i]) > order.indexOf(b[i])) return 1;
                if (order.indexOf(a[i]) < order.indexOf(b[i])) return -1;
            }
            return a.length - b.length;
        }).join('') === words.join('');
    
    // Returns boolean
    return newArr;
};
```

One down, 31899835 left to go! 

Thanks for reading, <br>
Indy


