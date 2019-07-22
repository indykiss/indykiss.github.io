---
layout: post
title:      "Datascape- to see how a company's stock prices are doing"
date:       2019-07-22 22:08:50 +0000
permalink:  datascape-_to_see_how_a_companys_stock_prices_are_doing
---


Data scape is a stock price CRUD tool that allows users to create a scape that shows a company's name, stock ticket, start and end dates.

At the moment, my app is missing the delete and update aspects, but the app fundamentally allows users to create a scape. 

Ideally, in the future, there will be an external API fetch that pulls down the company's stock prices for the user's selected days. It will also integrate a data visualization library to add on a pretty graph so the user can easily see the stock price trends for that time frame. 

Extra down the road, I'd like to add in another external API that illustrates the company's main S&P industry indices to help show the user how a company is doing against their competitors. Lots of work needs to be down, but I've started pulling the first external API thought process (just pulling stock ticket close prices) in a previous attempt at this project. 


I feel like this project has been my rockiest, in that I've been struggling with setting up the files for success and understanding the role of redux in react. I understand that redux acts like a store to help manage the data. The process between how the data goes from components/ actions / reducers/ store/ containers is a little confusing for me. My rack-cors was a mess for the first two repositories. My webpacker didn't work for the third and fourth repo. The fifth was finally done well, mainly after getting in touch with some classmates and section leads who pointed me towards a few good react-redux explanation videos. 

If I were to start the project over again, I would immediately turn to these two videos to guide me: 
https://www.youtube.com/watch?time_continue=13&v=nnqmLFop8Cg
https://www.youtube.com/watch?v=9KrrlWy1E_A
(Would've saved so many hours, days... a few weeks). 

But that's ok, I've learned from the initial mistakes that I've made. 
