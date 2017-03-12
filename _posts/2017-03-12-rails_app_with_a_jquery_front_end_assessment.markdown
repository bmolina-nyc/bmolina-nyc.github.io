---
layout: post
title:  "Rails App with a jQuery Front End Assessment"
date:   2017-03-12 17:48:08 +0000
---

I am finished with this assessment and about ready to venture into the final modules of the Learn curriculum - React and Redux.

This section of the course was particularly difficult and frustrating.  The need to push past your comfort zone is definitely important when learning to code but the javascript section has so many labs where they show you how to do something and then the lab itself became not only a lesson in that fact, but also an introduction into some new components that were way above and beyond anything the curriculum shared.  Much of it was so odd and right when I was about to start this lesson, I got an email noting that the Javascript section was getting redone and React was now going to take the place of Angular JS.  I was very happy that I didn't start Angular yet but I was also annoyed that my JS experience could have been alot better than it was.

That being said - I started this assessment project with a bootstrap layout and then tossed it after a few days since I was having trouble getting some basic authentications to work within the constraints of the divs that bootstrap creates.  I figured it was best to try to make any html and css on my own until i get comfortable enough understanding why things move and work they way they do on the page.

My app starts with a basic homepage that allows a user to either signup or login.  This became my first bit of jQuery in my app: The page has two rails forms using the form_for helper.  These were then wrapped in separate html div's and given a style: display:block for one and display:none for the other.  Using jquery, I was able to toggle between hiding the signup form and showing only the login, or vice versa.  It was a simple little trick but as a person with one month of js and jquery under my belt, it felt pretty cool.

Once authenticated via login (bcrypt gem) - a user is taken to an index page with various vacation options. Using jquery, I generated random prices for these trips and the user can then go to each trip individually and check the weather in that city (via an API get call to a weather provider I looked up), and also make comments on that particular trip.  The user is also able to scroll through all the trips one at a time.  There isn't any specific rhyme or reason to the app at this junction, I really just wanted to get the requirements to work!  On a refactor, I probably would go back and allow somebody to save trips to their profiles or purchase the trip at the cost that was generated through the method calls on the prototype.
