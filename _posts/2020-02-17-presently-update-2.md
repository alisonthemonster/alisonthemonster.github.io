---
layout: post
title:  "Presently: 2020 Update"
date:   2020-02-17 19:45:31 +0530
categories: ["projects", "android", "presently"]
---
Presently is an open source [gratitude journal for Android](https://play.google.com/store/apps/details?id=journal.gratitude.com.gratitudejournal&hl=en) that I started building about a year ago. We are launching a bunch of new features this month and I wanted to share them here!


### New Features
  - Biometric Authentication
    - Now users can lock their entries using biometric authentication. This feature is Presently's first opens source contributed feature! Many thanks to [Alon](https://github.com/lalon) who contributed this much requested feature and to our many beta testers who helped us get this ready for production. <br>
 <img src="https://i.imgur.com/LP05FnP.png" width="400"> 
  - New themes and theming updates
    - I revamped our themes settings view to give a better representation of what applying a theme would look like
    - I also added several new themes to the app and we now support colorful icons in themes
<img src="https://i.imgur.com/2Vdk5ay.png?1" width="400"> 
  - Milestones in your timeline
    - When a user reaches a significant milestone, like writing five gratitude entries, I show them a congratulations dialog to celebrate their acheivement. Now users can be reminded of their progress by seeing their milestones in their timelines.
<img src="https://i.imgur.com/3kJmSTD.png?1" width="400"> 
  - New Languages
    - Since the last update here volunteers have helped us translate Presently to 10 new languages! We now support Spanish, French, Italian, Slovak, Arabic, German, Polish, Portuguese, Russian, and Finnish. Thank you so much to our brilliant volunteers for their time and excellent work.
  - Espresso testing and Firebase Test Lab
    - UI testing was long overdue for Presently but I had prioritized other feature work first. Over the holidays I finally got a chance to dedicate some time to improving our code coverage through automated UI testing with Espresso.
    - Tests run on every pull request on a device in Firebase Test Lab and are reported back along with code coverage numbers.


Check it out here in the [Google Play Store](https://play.google.com/store/apps/details?id=journal.gratitude.com.gratitudejournal&hl=en)
 and look at my source code on [Github](https://github.com/alisonthemonster/Presently)!
