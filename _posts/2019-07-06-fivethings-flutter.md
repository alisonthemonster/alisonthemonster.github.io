---
layout: post
title:  "Five Things in Flutter"
date:   2019-07-06 19:45:31 +0530
categories: ["projects", "fivethings", "flutter"]
---

Since going to Google IO back in May I was so excited to try out Flutter. I came back from IO and took [App Brewery's Flutter course](https://www.appbrewery.co/p/flutter-development-bootcamp-with-dart) (excellent course, highly recommend!) and then started to think about what I wanted my very first Flutter app to be. 

I've been working on various aspects of my Five Things project since 2017 and the current version had been feeling a bit stale. I decided it was time to give **the mobile UI a refresh and to integrate with Google Cloud's sentiment analysis tools**.

In just 21 days I was able to build a fully working app and the backend to support it. Flutter development is FAST. Here's the final result:
<blockquote class="imgur-embed-pub" lang="en" data-id="a/7cjfyFD" data-context="false" ><a href="//imgur.com/a/7cjfyFD"></a></blockquote><script async src="//s.imgur.com/min/embed.js" charset="utf-8"></script>

### Features
- A monthly dashboard
  - The monthly dashboard shows you an overall view of a month. It has all the days you've written for that month along with the sentiment scores for those entries
- Search
  - I used Algolia to index my data and make it searchable
- Sentiment Analysis
  - When the user writes a complete entry we analyze the sentiment of the entry and send it back to the user.


### Architecture
After lots of research and experimenting I settled on using the [BLoC pattern](https://github.com/felangel/bloc) for this app. I chose this library because of it's fantastic [documentation](https://felangel.github.io/bloc/), it's similarity to MVI in Android (a pattern I'd been already researching), and it's great tutorials. 

In the BLoC pattern your app responds to `events` and outputs different `states` accordingly. BLoC is built upon Dart's Streams and RxDart and allows you to properly separate your business logic from your presentation logic. 


### Backend
- Firebase Cloud Firestore
- Cloud Functions
  - Call the Google Language sentiment analysis endpoint when a new, complete entry is written and writes the response back to the database
  - Index new entries with Algolia
- Firebase Authentication

### Summary
Working with Flutter is exciting and fast. I was able to build a prototype so quickly and was able to build it following architectural best practices. This was a great exercise and I look forward to what I can build next!