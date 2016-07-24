---
layout: post
title:  "CLI Data Gem Project - cats cats cats"
date:   2016-07-24 22:27:55 +0000
---

This project like all recent Learn projects for me have taken a bit longer than I would like but once I get into it, I can usually make very good and meaninful progress. Cursed 9-5 job!  Anyways, for my Gem - I currently have the CLI running cleanly and scraping a list of the first 8 cats from the homepage of adoptable cats listed on the ASPCA website http://www.aspca.org/

I'd like to start by saying that this was very frusterating and cool at the same time. I never imagined doing stuff like this before and with only a few short labs before this, I was able to make this thing come together pretty decently.  I still am awaiting assessment review and know refactors need to happen but i'm just happy with the current progress.

I started this project sometime early last week and probably should have just watched Avi's video right from the start.  My initial thoughts were to copy the skeletons of the example gems he and another student put together, and then write my own code in place of theirs.  Not a good idea - constant unitialized constant errors from all my namespaced classes.  I decided to watch the video and code along and sure enough, there is a bundler gem that creates the skeleton for you. Duh- I wasted an evening messing around with a sloppy framework but its always good practice in the end to need to create files and directories straight from the cmd line.  

Once I had a skeleton in place and followed along in regards to the dependencies and how certain files need to require eachother as relatives to work (still a very new concept in my head as far as tying them together), I was impressed that I was able to get the "fake data" to run.  All that was then needed was for me to take the method ideas Avi was creating and make them my own.  

My current gem isnt final its just working - after code review im sure much will change. All the Cat instance logic and the Scraper logic are within the same Cat class right now.  So in viewing the ASPCA page for cats, there are a few things you notice right away - Each cat has its own profile pic in an index page, and within that page is a bunch of biographical details about the cat. So I needed to 
a) create a method with Nokogiri that would find the HTML div's where I could harness the outbound URLs for each cat on its index page as the return value 
b) create another metho that would harness the URLs of each individual cat and then scrape the elements that will make up the attributes of the cat instance
c) have all those new cats listed in a single array so I could play with them in the CLI

Scraping takes the longest time and thte biggest bugs I found with this program are the fact that not every Cat has exactly the same type of descriptive information on its respective bio page.  The main place of difference was their bio stories. Some cats had little to no bio and others had multiple paragraphs (all separated into their own <p> tags). So I needed to get creative with my nokogiri scrapes and ask for all the paragraphs where a story might exist

cat.story = doc.css("div.field.field-name-body.field-type-text-with-summary.field-label-hidden").css("div.field-item.even").css("p")[1..5].text 

and then gsub out the unncessary paragraphs so that the paragraphs remained uniform across all cats.

I like how Avi approaches the program.  It really is important to stop trying to make determinations on code with information I don't have. Starting with the bin and executable files as well as the command line really helped to keep me on track and progressing on this lab.  Also good in this lab was the reinforcement of basic github commands in my memory as it is really one of the first labs in the program where you need to push your own commits without using "learn" as a shortcut. I look forward to the refactor and any other ways of tightening this thing up!
