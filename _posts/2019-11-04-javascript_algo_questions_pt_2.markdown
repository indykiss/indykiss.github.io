---
layout: post
title:      "JavaScript Algo Questions Pt. 2"
date:       2019-11-04 20:32:14 +0000
permalink:  javascript_algo_questions_pt_2
---


As a continuation of my blog series around answering algorithmic questions, I'm going to do a bit of a spin and start incorporating product cases scattered here and there. So not *really* an algo question, but more like a "practice how to think about a complex issue" question, which can be applicable in particularly gnarly algos, so I feel justified in calling this a part of this series. :) 

In my current role, I spend a chunk of time writing out cases, looking at all the variables that a project team considered when planning out sprints, how the team executed each phase of the project, and the resulting deliverable and client impact. There's good value in understanding how to bridge gaps between conflicting interests and in consolidating processes to gain maxmize efficiency. Break the data silos! 

I'm going to start with one product case study, then move on to a couple more traditional algos for this week's article. 


### Product case #1

<br>

*How would you improve LinkedIn’s sign up onboarding process?*

1. I would begin with an audit of the current onboarding process, determining the variance of experience for users of different backgrounds. Is the process similar for Macs vs. PCs vs. Mobile? How is the process for signing up through the various third party integrations; Google, Facebook, etc, if applicable?
2. Another addition to this audit would be understanding how the users currently view the process and gather metrics around the current state of affairs (customer sentiment, ease of onboarding, etc). Any complaints would be considered high priority. This would be done by interviewing users about the process in focus groups and also doing a quick market research study to determine both their perceptions and their actual behavior. 
3. When we have the current metrics, I would outline a goal for post-process improvements of those metrics that is both attainable and agreed upon amongst stakeholders. 
4. Once I've gathered information about the current process, I'd note situations where there's friction. If the mobile sign up's process is a few too many steps, if the touch responsivity of a button isn't on point, if the screen UI is too zoomed out/in, etc. With this information, I'd note each segment that needs improvement, then prioritize to ensure the top concerns are resolved, as occasionally not all issues can be addressed with the given time and budget. 
5. After each note has been taken, I would create a roadmap with detailed thoughts for each improvement-needed-segment. For example, if we take the issue with the touch sensitivity of a button, I would touch base with the product owner of that particular functionality. I'd also like to chat with the programmers that create each function to get their input around the feasibility of erasing those technical friction points. 
6. With each piece of friction addressed by adding in key stakeholders' buy-in, I'd evaluate the time frame that the whole process would take to meet standards. 
7. When the fixes have been added into the system, I would then create a beta group of users to test out the new functionality and do in-depth surveys/ interviews/ market research to understand if these add-ins had improved the process. Metrics (same as the initial data pull) would be gathered.
8. I would compare the metrics from pre- and post- system change to see if this processs needs additional iterations. 
9. If the metrics show improvement, I would gather with stakeholders to see if the amount of improvement is sufficient. If not, then we would review the process again to note where is the unaddressed friction, then rinse and repeat until the system is in a better place.
10. At the end of the project, I would create documentation to note what the above process was, what was learned, the metric improvements, what can be done in the future to make a similar intiative more effective, etc. This documentation would then be tagged accordingly for knowledge management purposes, then added to LinkedIn's main intellectual capital repositiory. 


### Back to your regularly programmed (pun intended) algos


*Anagrams!<br>
Check to see if two provided strings are anagrams of eachother. One string is an anagram of another if it uses the same characters in the same quantity. Only consider characters, not spaces or punctuation. Consider capital letters to be the same as lower case.*

```
function anagrams(stringA, stringB) {
   return anagramMapHelper(stringA) === anagramMapHelper(stringB)
}

function anagramMapHelper(str) {
  return str.replace(/[^\w]/g, "")
  .toLowerCase()
  .split('')
  .sort()
  .join('');
}
```


*Capitalize a string. Example: <br>
capitalize('a lazy fox') --> 'A Lazy Fox'*

```
// Runtime: O(n) because there is a single loop. Increase in input by 1 equates to equal increase in processing power. 

function capitalize(str) {
  const arr = []

  for (let ele of str.split(' ')) {
    arr.push(ele[0].toUpperCase() + ele.slice(1))
    }
  return arr.join(' ')
}

```




Thanks for reading!<br>
Indy 

