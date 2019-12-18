---
layout: post
title:      "Off the Rails - Diving into the JavaScript Project "
date:       2019-12-18 01:43:24 -0500
permalink:  off_the_rails_-_diving_into_the_javascript_project
---


For my JavaScript project, I decided to focus on another passion beyond my traditional rock climbing related applications. Opting for a more popular pastime, I built an application geared toward sharing and inspiring visits to U.S. National Parks. Hoping to ultimately capture a broader user base of hikers, climbers, fishermen, and trekkers of all sorts, this is a very lightweight application that provides information and user experiences for individual National Parks. 

Trekker allows users to browse all 61 National Parks, which each include their location, year established, a (hopefully) engaging summary, and a nice photograph. Each park has it's own "card" containing it's information. By mousing over the picture, the user can reveal the park's summary. This was one feature that I was very excited to implement and, fortunately, it turned out to be easier than expected. At first I was uncertain how to approach the event listener, but with some digging through Stack Overflow I uncovered an interesting way of approaching it. By simply calling .onmouseover and .onmouseout on the container, I was able to easily implement the code to achieve the desired toggling effect. It was great to learn such a simple and elegant solution for something I was initially very worried about attempting. 

Trekker also allows users to input visit experiences with the park name, visit date, and personal notes. These notes are intended to be insightful and help to inform fellow trekkers of the good and the bad about each park. Users are able to search the cumulative visit log by park name to view only the feedback for that specific park.

My biggest challenge came with feeling obligated to see through my original vision for this application, despite obvious and massive struggles to achieve certain unnecessary features. Though I initially implemented JWT user authentication, I ran into several issues that I spent hours fruitlessly toiling over, only to break integral parts of my program or become hopelessly confused. In the end, I had to consider the best application that would A. incorporate what I've already learned and researched, while rigorously using and testing those skills B. challenge me without overwhelming me, and C. meet the requirements as well as satiate my hopes for the program. Overall I am pleased with the end result, though admittedly, I am excited to continue growing so that I can continue to expand upon this project. 
