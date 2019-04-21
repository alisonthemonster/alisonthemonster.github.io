---
layout: post
title:  "Five Things Android UX"
date:   2018-11-17 19:45:31 +0530
categories: ["android", "fivethings", "design"]
---

I've had a lot of fun playing around the with designs and UX of the Five Things mobile app. Its come a long way from its initial designs and now features lots of great material components, illustrations, and animations. Below are all the various iterations the Five Things mobile UX has undergone:

- [Initial Design](#initial-design)
- [Second Iteration](#second-iteration)
- [Third Iteration](#third-iteration)
- [Current Design](#current-design)
- [Sketches and Ideas](#sketches-and-ideas)


### Initial Design
The initial design of the Five Things mobile UX was very similar to FiveThings.me. It had five text boxes, a date that when clicked would reveal a calendar, and a hamburger menu that would open a navigation drawer. It also featured potential book cover designs that were hosted on Firebase storage (read more about [Five Things Books here]({{ site.baseurl }}{% post_url 2017-07-03-pdfgen %}))

<img src="https://i.imgur.com/rkX3EZ7.png" width="240"> 
<img src="https://i.imgur.com/c35QxFl.png" width="240">

### Second Iteration
With the rewrite of the backend, new authentication screens needed to be added. 

<img src="https://i.imgur.com/88PeyDr.png" width="240"> <img src="https://i.imgur.com/vp1vPSr.png" width="240"> <img src="https://i.imgur.com/YY17Sf1.png" width="240"> <img src="https://i.imgur.com/CXZXfVX.png" width="240"> <img src="https://i.imgur.com/pfmj7Jo.png" width="240">


### Third Iteration
Once the backend was all rewritten I had lots of time to focus on the UI and UX. The backend switched to Google Sign In, so the sign in screens were replaced with a single button and a viewpager with illustrations I drew. I also made a few illustrations for error and empty states. 
I changed the navigation style for entries from left and right arrows to a swipe navigation (using a viewpager) and implemented an autosave feature.
This iteration also added a light mode and some minor UI tweaks. 

<img src="https://i.imgur.com/ZveoZNN.png" width="240"> <img src="https://i.imgur.com/p5suUk7.png" width="240"> <img src="https://i.imgur.com/YCPxu9J.png" width="240"> <img src="https://i.imgur.com/L369U1l.png" width="240"> <img src="https://i.imgur.com/r139CAZ.png" width="240"> <img src="https://i.imgur.com/RBo5wok.png" width="240"> <img src="https://i.imgur.com/rJWvpJ4.png" width="240"> <img src="https://i.imgur.com/JOdqozW.png" width="240"> 

<img src="https://i.imgur.com/x1xjZOM.png" width="720">


### Current Design
Inspired by my time at the Android Dev Summit I came back to the Five Things app and did some big redesigns. I updated the navigation from <img align="right" src="https://i.imgur.com/7dZZ6Wa.gif" width="400"> drawer navigation to the shiny new Bottom Navigation using the Material Components library. And taking inspiration from the Google Home app I added a Floating Action button to my bottom nav that would open up the calendar to select a date. From the excellent talks about animation and specifically animated vector drawables I created the navigation icons and animated them when clicked. 

This iteration also began to experiment with an analytics dashboard.

In the future I plan to finish out the analytics dashboard with other key stats. I'd also love to support designing your own book through the app. 

<br><br><br><br><br><br><br>

### Sketches and Ideas
I keep a notebook where I've written down all my ideas for Five Things Designs, here's a few of my sketches before I built them out:

<img src="https://i.imgur.com/vpQ3AcK.jpg" width="300">
<img src="https://i.imgur.com/hYlGd9i.jpg" width="300">

<img src="https://i.imgur.com/GSk8wmV.jpg" width="300">
<img src="https://i.imgur.com/PgnNgnC.jpg" width="300">

<img src="https://i.imgur.com/7ngKLNR.jpg" width="300">


