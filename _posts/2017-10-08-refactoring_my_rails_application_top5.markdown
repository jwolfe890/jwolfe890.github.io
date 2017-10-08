---
layout: post
title:      "Refactoring My Rails Application Top5"
date:       2017-10-08 16:52:40 +0000
permalink:  refactoring_my_rails_application_top5
---

Recently, I did a major overhaul of the application I completed for my Rails assessment – Top5. In the process, I learned a tremendous amount about my growth as a programmer, and increased my confidence and facility with Rails. 

1. Becoming a great designer undoubtedly requires not only creating projects, but also revisiting and refactoring them, because in that process you come to understand why many of the unwritten rules are there in the first place. 

2. Somewhere in the curriculum it provides a warning about using Devise because of the dangers of customization. Since Devise is somewhat complex, my biggest worry in refactoring this project months after I made it were potential Devise errors. I had forgot many of the interworking of Devise.

3. I was really happy to discover that my ability to understand SQL and complex Active Record queries had improved immensely. Whereas before I would have been frightened, now I had not problem implementing something like: @recent = List.joins(:topics).merge(Topic.where(id: params[:list_topic][:topic_id].delete_if(&:empty?)))

4. If you’re trying really hard to something in ruby/rails and the solution feels taped-together, it’s usually because you’ve made a fault design decision.

5. The experience of just seeing others’ code greatly expanded what I learned was possible and in putting this project together I had much more tools at my disposal than when I initially started. 

6. Originally, I designed the application with authentication in mind, and built out features that revolved around a Users controller, because I had in mind an experience that would exclude lists the users made in some situations on a dynamic profile page. However, when I refactored the project, I wanted to make these features available for people not logged in, which is when I learned that it’s harder to make a project less restricted after the fact; so in the future, I would have built out the project – even if not initially intended – with the possibility of adding the features to non-authenticated users at a later date. 
 


