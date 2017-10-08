---
layout: post
title:      "Adding JSON to My Rails App"
date:       2017-10-08 16:55:03 +0000
permalink:  adding_json_to_my_rails_app
---


After completing my Rails app, I added JSON functionality to it. While I was experienced with JSON from the Learn Verified labs, adding it to my already complex rails application adding some new challenges.
I first underwent rendering the index page through JSON. I initially tried .fetch, but after finding some complications with this approach and devise, decided to use $.ajax for the get request. Although I had a document.ready function in file, I also had to add one to this query, because the event handlers were being lost when I returned to the page after clicking on the home link.
Once I rendered links of all the Lists to the page, I next set about rendering the show page of the Lists. Along with the show page of the lists, I also a rating template for each list through .get requests. Additionally, I tapped into the List has_many through relationship to include list_topics on each show page. I additionally added a Next button that would allow the user to search through the Lists sequentially.
The most complex part of this process was creating the ratings template and partial to ensure that once a user submitted a rating through a post request, the average rating would be updated on the page. Throughout the process, I implemented an assortment of JS prototype functions as a means of cleaning up the code in the JSON queries, as well as to add increased functionality in Jquery.
Ultimately, this was a great learning experience, but in the future I will never add JSON after the core of an App has already been designed.
