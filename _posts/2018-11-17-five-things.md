---
layout: post
title:  "Five Things"
date:   2018-11-17 20:45:31 +0530
categories: ["android", "projects", "fivethings"]
---

**Five Things is a daily journaling project** where at the end of every day you write down five things that happened to you. I started this project on January 1st, 2016 with a handwritten daily entry. I was able to find time to write most days but when I was away from my notebook I would jot down my entry on my phone. Over time more and more entries were written in my phone and not in the notebook. That was when I built a web client to keep a journal on the go. Since then I've iterated several times on backends, authentications, and designs. Below is the timeline of the project and its current plans:



### May 2017 - November 2017: Web client
<img align="right" src="https://github.com/alisonthemonster/FiveThings/blob/master/static/images/Screen%20Shot%202017-11-08%20at%2010.32.56%20PM.png?raw=true"  height="260">
The web client was written in vanilla Javascript, Node, and built with a Firebase backend. It uses Google Sign In and the Firebase Realtime Database. Users can log in, write new entries, and view their old entries. I still use this website every day to write down my Five Things.



### July 2017: Experimenting with physical books
<img align="right" src="http://i.imgur.com/kMMbRY9.gif"  height="240">
After some time of writing digital entries I missed the feeling of a physical journal. I realized that I could take my entries (in JSON format) and generate a PDF that could be printed and turned into a physical book. I started to play around with [PDFJS](https://github.com/rkusa/pdfjs), a PDF generation library, and generated a few different book styles. This was great as I got to experiment with visual design and I spent a lot of time sketching and dreaming up new book designs.   

Read more about PDF generation and my design process [here]({{ site.baseurl }}{% post_url 2017-07-03-pdfgen %})!

### December 2017 - February 2018: Android Client Phase 1
I decided to rebuild the Android client this time with Kotlin. It was my first time using Kotlin and I learned a lot here. Again it used the Firebase Realtime Database and Google Sign In. I used the brand new Android Architecture components and followed an MVVM architecture. It had a swipe navigation to move between days and a navigation drawer to access the other views.

### April 2018 - September 2018: Android Client Phase 2, the new backend
Inspired by great apps like Daylio, I realized I could measure the sentiment of my entries and chart it over time. I began to work with a friend to build out a new backend that would be able to support sentiment analysis better than the Firebase Realtime Database. This meant rewriting authentication, using Retrofit/Okhttp to make the requests to our own server instead of Firebase, implementing a new search feature, and of course building out the new analytics feature.

Read more about this phase of the Five Things Android app [here]({{ site.baseurl }}{% post_url 2018-04-15-fivethings %})!

### September 2018 - November 2018 Android Client Phase 3: A visual redesign
Once the new backend was fully implemented I could focus on UX. I designed a series of onboarding illustrations, error states, and focused on animations. At this time I also updated the navigation to a Bottom Navigation Bar with a FAB to open the calendar. 

Read more about the UX of the Five Things Android app [here]({{ site.baseurl }}{% post_url 2018-11-17-fivethings %})!

### Today and beyond
Work on the Five Things project has stopped for now. I still use the Five Things website every day and plan to for the foreseeable future. There is still work to be done to support sentiment analysis and I have plenty of ideas for book designs to implement. 
