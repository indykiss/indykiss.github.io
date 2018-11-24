---
layout: post
title:      "Book scraper"
date:       2018-11-24 22:27:59 +0000
permalink:  book_scraper
---


I finished my first actual project! 

My web scraper takes the top 50 books on the https://thegreatestbooks.org/ list and presents the titles and ranks to the user. Then the user can select a rank (1 -50) and then be provided the title and a short description of the book. 
The user can continue selecting ranks to get more book titles and descriptions infinitely, until they type exit. 

Ex:
Welcome to the web scraper!
We have the following books:
**insert list of the top 50 books**
Please input the rank of the book you'd like to learn more about, and we'll provide name and a short description. Or press exit. 
User input: 1
Your selected book is:
**In Search of Lost Time by Marcel Proust**
Here is the beginning of the summary:
**Swann's Way, the first part of A la recherche de temps perdu, Marcel Proust's seven-part cycle, was published in 1913. In it, Proust introduces the themes thatrun through the entire work. The narr...**
Please input the rank of the book you want and we will provide name and description. Or press exit.

My web scraper uses three classes to do this:
* CLI class- Simply provides the CLI interaction with the user. Welcomes the user, calls on methods within the other two classes, then exits the program/ says bye. 
* Scraper class- Uses Nokogiri and HTTParty to scrape the web page to get the HTML from the external source. I used HTTParty instead of open-uri because I enjoyed the *"When you HTTParty, you must party hard!"* output after typing "bundle install." It's the little things. 
* Book class- Takes the HTML from the Scraper class and makes two sets of arrays with this information. Then this class outputs the index of the arrays, depending on what index the user wants. 
 
I wasn't entirely sure how I wanted to display the information, so I thought having two arrays would be the best way to make the information easily accessible and changeable later on. One way to further this project is to separate title and author with "by" (all book title listings are "Book title *by* author") as a .split and allow the user to get three sets of information, or the user inputs title and gets back author/ description. 


## Obstacles
The first obstacle was just getting the right elements scraped from a web site. I used a few (then got kicked out...  *cough Amazon cough*) before stumbling upon thegreatestbooks.org, recommended by my awesome TA Antonio. 

One of my main obstacles was to get the scraped output to be readable. I played around with the regex to get the correct values added to the title and description arrays. 

Once I had the right elements in the arrays, I had another issue accessing them. In my Book.scraping_page method, I had an extra step for my description array to be more readable (the web scraper grabbed a few extra elements for every actual description; for example attributing the description to either the publisher or wikipedia made an extra element in my description array). 

My final, ongoing, obstacle is the fact that the last index of the description array outputs no matter what after the user types exit. Definitely not ideal behavior, but will work on as I wait for my project review. Another obstacle is my formatting-description-array-methods cutting one of the actual descriptions into parts (the last description too!) I was tempted to just prompt the user to only input 1-49, since those work fine (but that's not a good habit to keep so will fix soon).



That was fun, can't wait for my next project!

See my full code here!
https://github.com/indykiss/ranking_scraper






