---
layout: post
title:  "building my CRUD application"
date:   2016-09-26 02:24:15 +0000
---

This project felt pretty imposing at the onset because up to this point, 99% of the labs in the Learn curriculum will already have the project stubbed out with the majority of the folders and necessarily directories already laid out for you.  With so much to absorb, it was a bit scary to have to create all these folders and directories and startup files by myself - stuff like the gemfile, config.ru and all the under the hood items.....the last thing I wanted with my study time was to have to spend hours just setting up the file to run properly.  I had that issue when trying to get the CLI gem assessment off that ground  but to my surprise, after installing all the necessary gems and copying the setup of the fwitter assignment, I was able to get my new app off the ground and i successfully created the tables, models, routes and ultimately the initial index page - it was great to see that 200 code without any drama!

My app allows a user to login and create Rosters and Players for that Roster. A User can Read all Players and Rosters but the User can only Update, and Delete Rosters and Players that he created (ok im gonna stop capitalizing my Models lol).  A user can edit the players he creates but once that player is on a roster he didn't create, he is no longer able to edit that player since he no longer has the "ownership" of the player. I created logic to make sure that the correct user had the power to update or delete things he created. I also made sure that the forms were properly filled out to make successful updates across the application.


