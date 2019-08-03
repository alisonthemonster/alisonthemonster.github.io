---
layout: post
title:  "Presently: What's new?"
date:   2019-08-03 19:45:31 +0530
categories: ["projects", "android"]
---
Presently is an open source [Android app](https://play.google.com/store/apps/details?id=journal.gratitude.com.gratitudejournal&hl=en) to record daily gratitude entries. It's been a while since the initial release and I thought I'd post on update on all the new features and things I've learned along the way.

### New Features
  - Search your entries using Room's FTS
    - Room introduced FTS back in late 2018 and it allows you to search through your data by creating a searchable virtual table. [This blog](https://medium.com/@sienatime/enabling-sqlite-fts-in-room-2-1-75e17d0f0ff8) was incredibly useful for setting it all up.
  - Calendar navigation
    - Many users had left reviews or reached out to me asking for a way to quickly move to old entries or to add an entry for a day further in the past than yesterday. I had a lot of fun here playing around with animations and working on the motion for opening the calendar.
  - Themes
    - Picking the initial color scheme was such a hard choice that I knew from the start that I wanted to support multiple themes. I had a great time playing around with colors and I expect I'll be adding new themes in the future.

### Demo
<blockquote class="imgur-embed-pub" lang="en" data-id="ad3PeDt"><a href="//imgur.com/ad3PeDt">View post on imgur.com</a></blockquote><script async src="//s.imgur.com/min/embed.js" charset="utf-8"></script> 



### Presently App Website
I also threw together a quick little demo website for Presently [here](https://presently-app.firebaseapp.com/).
![Website Screenshot](https://imgur.com/k8jCUdD.png)


Check it out here in the [Google Play Store](https://play.google.com/store/apps/details?id=journal.gratitude.com.gratitudejournal&hl=en)
 and look at my source code on [Github](https://github.com/alisonthemonster/Presently)!
