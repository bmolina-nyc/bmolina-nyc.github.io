---
layout: post
title:  "Rails Assessment App - Adding Devise for Authentication"
date:   2017-01-03 03:01:28 +0000
---


Learning to code will trip you up to no end but as long as you continue to stick with it, you'll eventually come to some understanding of the roadblock you hit.  What I find is that an insane amount of practice, and a million mistakes along the way will get me closer to understanding something and more importantly, knowing how to look up and identify a solution to any wall I encounter.

The Devise gem was one of those walls for me upon hitting that section of the curriculum.  Because so much of Devise is stubbed out automatically for you upon installing the gem, it's really hard to understand what is happening under the hood and that is insanely frustrating as a semi-beginner!  What I found however was that there are a few small tricks you can do to make your life alot easier when playing with Devise.

As we all know - Devise in a nutshell, is a ruby Gem made by really smart people, to simplify alot of the needs of authentication.  In the case of my rails assessment app, I only really needed to give my user the option to authenticate, register, and have omniauth access via Facebook. So you start with the basics:

1- add the gem to your gemfile - *gem 'devise' *
2-  install devise to your app - *rails generate devise:install*
3-  Create a user model - *Rails g devise User*

after running the migrations created from all of this - Devise is basically good to go. You can login, you can logout, you can edit a users information. All you really need to do is add the devise path's links to a section of your application that makes the most sense. For starters, you might want to create some static homepage view through a Static Controller, where you could set up the link for a user to start a new Devise session via the "new_user_session_path" url helper.

So all of this is very cool but where is the code that is making this whole thing work so easily? Your User model will come filled in with items like :database_authenticatable, :registerable, :rememberable, :validatable, etc but where is that all actually happening?

The lessons don't mention this but something that really helped me to understand Devise was entering this command 

***rails generate devise:views***

Add this to your app from the command line and you'll see the views section of your app populate with all the devise views that were happening under the hood from your entry of the previous 3 commands.  There laid out, is the code for the sign in views, the new registration views, the change your password views, and a bunch of other views you may or may not want to use in your app. If you add stuff to the view pages (extra text for starters), you'll see the devise views updating.  You won't really need to change anything since the views are all set up to go out of the box, but its a big help to see how it works as opposed to just setting a few lines of code and not really getting where its going since the devise views do not generate from the 3 commands above.
