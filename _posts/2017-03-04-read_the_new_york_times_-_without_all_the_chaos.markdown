---
layout: post
title:  "Read the New York Times - without all the chaos"
date:   2017-03-04 16:58:07 -0500
---


This project was the most rewarding coding challenge I've undertaken. Probably most of that has to do with the fact that it was my first final project, but I think it also has to do with the fact that I chose to create something I actually wanted to create. It changed and morphed a lot along the way, but I've now completed something I'm very happy with!

My first thoughts I've immortalized in my Notes.MD file, but in simpler form, I originally wanted to pull from both the New York Times and the Washington Post, give the user a choice between publications and then print the articles from within one publication, then have the user pick an article to read. 

This changed for a couple of reasons. The first was that as I was working, I realized it would probably be easier to build it out just for one publication and then add in the other publication. The reason why the Washington Post isn't included now is just because I figured that this fulfilled the requirements and I have a long drive back to New York ahead of me tonight and wanted to submit it now. That is something I would be perfectly happy to add in though. 

Setting up the Gem file was definitely the scariest part for me. I watched the video of the CLI Data Gem Walkthrough, so I figured out how to create it and then I accidentally messed up uploading the files to GitHub and creating a repository there, but it all worked out in the end clearly. It was just a lot of trial and error and really learning! With a lot of the Learn tests, sometimes the answer is really kind of right there, but this time there was some googling on how to upload a new file to Git and stuff like that. It was really scary, but awesome at the same time. 

I really followed the workflow of the video, a) because I wanted sort of a backup to know how to check my setup if something went wrong and the troubleshooting in the video helped me troubleshoot on my own, but b) the video's workflow really just made sense to me. So, after I had my files set up, I made sure that my bin was working correctly and I could use the command `./bin/daily-headlines` to check all of my code!

Then, I started building out the interface! I set up all of my methods to show what I would want the program to do in my cli.rb file. I set up a call method that would call all of the other methods. I wanted a menu to list all of the articles and allow a user to select an article, then selecting an article to read prints out the URL of that article so that the user can copy and paste the link into their browser to read it. 

After that, I had to go about defining my class of Articles and scraping to create the articles. This was a bit of trial and error and I ended up not including the blurb because the id changed on me at one point and it was no longer working and I decided just the headline was enough to lead the user to the URL. That's certainly another thing I could expand upon for this project. 

However, I went through a lot of trial and error and inspecting the New York Times's website making sure that I was pulling all of the right info. I used `./bin/console` to check all of those commands and it worked out pretty well. Then, I went back into my `cli.rb` file and made sure that my methods were putting the right attributes of the articles and I think it all worked out pretty well! 

Like I said, this was very rewarding for me because this is a program I would actually like to have! Sometimes webpages like the New York Times overwhelm me and I just want to be able to read the headlines and pick an article from there so that's what I built. 
