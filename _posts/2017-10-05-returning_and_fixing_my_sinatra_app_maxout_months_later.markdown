---
layout: post
title:      "Returning and Fixing my Sinatra App MAXOUT Months Later"
date:       2017-10-05 06:50:16 +0000
permalink:  returning_and_fixing_my_sinatra_app_maxout_months_later
---


	When I reached the Sinatra project, like most people in the Learn program, I wanted to push myself and the possibilities of the project. In order to do this, I decided I would experiment with a complex join table (complex for my understanding of Active Record associations at the time). Therefore, I devised a join table that would not only join two models – Entries and Exercises – but also wanted to ensure that the join table – Exercise_entries – had values itself (weight and reps). These attributes on the join table were necessary because the Exercises would belong to many entries, so adding stats to each one would not be an efficient approach. 

	While at the time, I was able to effectively build the application – MAXOUT, an exercise app – I had to resort to some pretty tenuous looping methods in order to allow the user to choose which exercises they would include in the app and then add the reps and stats value they completed. I appreciated the finished product, but always was disappointed with that part of the project. After submitting my React final project, this week, I returned to the Sinatra project and within a few hours could immediately identify and change the taped-together code I had initially used to make it work. I was very happy because I recognized that my progress as a developer in the subsequent months had not only taken place in relation to my knowledge of frameworks, but also in terms of the way I approach and solve problems.  

