---
layout: post
title:  "Course Reviewing with Sinatra! "
date:   2017-06-30 08:28:02 -0400
---


The most important thing I'm taking away from this project is that I finished! For some reason, Sinatra was incredibly confusing to me with the MVC structure, but I've learned so much from making this project. 

My project is a website for course reviewing by students. It's three different models are users, courses, and reviews. Each user can create a login and sign in, sign out, and sign up. Each user has_many courses. 

Each user adds a course (or as many as they like) and then can attach their reviews to the courses. Each course has a professor and a capacity - the professor to identify who is teaching and then a capacity to give a ballpark for about how many reviews the course should have - no more reviews than number of students. Each course has_many reviews and belongs_to users. 

Users add reviews to the courses and reviews have a title and content. There is then also a box to input in which number course this belongs to so that it will be attached to the correct course. 

There are four different controllers, one for the application, one for the user, one for the courses and one for the reviews. Separating the different tasks out to each of the differnt controllers helped me so much to organize the structure and separate the different tasks out to which controller they should go to, rather than trying to push them all together and get confused. 

And then, there were all of the different views! I did take a leaf out of the book from the example assessment by expanding my layout.erb file - made some of the buttons look a lot better. 

The project is fairly straightforward - the process was a bit helterskelter. I'm a big fan of starting over and re-doing rather than troubleshooting and that caused me a lot of headaches while creating this. Ultimately, I'm very happy with this, though! 

