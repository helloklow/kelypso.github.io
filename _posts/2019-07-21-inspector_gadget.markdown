---
layout: post
title:      "Inspector Gadget"
date:       2019-07-21 07:22:32 +0000
permalink:  inspector_gadget
---


For our third project using Ruby on Rails, I created an application called Beta Breakers. This is an application for storing and sharing beta for outdoor activities, such as rock climbing and canyoneering. I hope to expand this project to also include hikes and mountain bike trails. "Beta" refers to the pertinent, technical information and details that allow outdoor athletes to successfully climb, rappel, hike, bike, or otherwise navigate their way through rarely-touched terrain. By breaking the beta (aka, sharing it via the world wide web), we can inspire the next generation of adventurers while also keeping the current generation safe and satiated with up-to-date information and new, exciting routes.

This was my first RoR web app and I was thoroughly impressed with the developer-friendly nature. At nearly every turn I expected to run into an impassable issue or become overwhelmed by my code, however the MVC architecture really helped me maintain a clear understanding along the way. Apart from the clarity that MVC's separation of concerns gifted me, my understanding of both CRUD actions as well as RESTful routes grew immensely by putting them into practice. "Rake routes" became one of my most valuable commands as I grappled with nested resources. 

While there were many excellent learning points throughout this process, the one that sticks with me the most relates to implementing omniauth (oauth). I spent an entire day tackling this problem alone. I had initially tried to apply oauth the very first day I started my project, however I quickly realized it was going to be a tricky beast. Despite watching all of the relevant Flatiron lectures as well as a half a dozen sources on YouTube, I wasn't able to get Google's oauth working. 

After walking away from the problem for a couple days (while building out the rest of my project), I knew that I would not only need a strong oauth strategy, but I would have to truly go the extra step to troubleshoot my own, unique issues along the way. Since I had run into countless issues with Google, I decided to try using GitHub's oauth instead. I spent many hours trying, yet still failing to get any strategy to work. I switched gears to try Facebook's oauth, sadly to no avail. Then, as I was watching Avi's oauth lecture for the third time, I caught one little knowledge nugget that I had previously missed. 

`raise auth_hash.inspect`

This simple line of code suddenly bust the issue wide open. I was quickly able to discern that for some unknown reason, GitHub's auth_hash was not passing my application the user's email, which my application needed in order to authenticate the user. As soon as I had this epiphany, I checked Facebook's auth_hash and low and behold, there was the user's email, as needed! I was in utter disbelief that I had spent nearly 8 hours on a problem that took a mere 10 minutes to fix, once I had the correct tool in my kit. Inspector gadget, to the rescue!
