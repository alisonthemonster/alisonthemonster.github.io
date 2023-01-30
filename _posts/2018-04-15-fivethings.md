---
layout: post
title:  "Migrating Backends in Five Things Android"
date:   2018-04-15 19:45:31 +0530
categories: ["android", "fivethings"]
---

Inspired by great apps like Daylio, I realized I could measure the sentiment of my entries and chart it over time. I partnered with a good friend to build out a new backend that would support sentiment analysis better than the Firebase Realtime Database.

Before this new backend, the app used Google Sign In and stored all the entries in a Realtime Database. My friend built a new backend using Python and Django that would support the following:
 - Email/Password sign in
 - Write/read entries
 - Searching your entries 
   - Data was indexed using ElasticSearch
   - Paginated results
 - Sentiment analysis for an entry
   - Sentiment score
   - Entity and people detection

Because the app was entirely Firebase up to this point this meant adding in Retrofit and Okhttp for networking and writing my own authentication. 
Adding in Retrofit and Okhttp was pretty trivial, and because I followed a repository pattern I was able to swap out my data fetching code from Firebase to Retrofit pretty easily. The tricky part was authentication.

#### Authentication

First there was the matter of building out the new account creation and account sign in screens, alongside all the client side form validation (and Espresso tests to go along with it!). 

We built his backend following the Oath2 protocol, meaning that I would need to work with Authorization Tokens <img align="right" src="https://i.imgur.com/V7yQueZ.jpg" width="300"> to make requests and work with his API. For an Android client this means using `AccountManager` which works through a series of callbacks to get the user's auth token. It's a complicated process with lots of potential error/success cases, meaning you have to be careful to handle them all. This is a sketch of my attempts to graph out the process. 
Building out the authentication flow was tricky but helped me understand Authentication and Oath2. 


As most software projects go, there was a major change in the backend in the middle of development. In my case it happened right as I had finished this new Oath2 authentication. Specifically after writing lots of cool UI tests and getting started on screenshot testing. We decided to switch back to Google Sign in using the AppAuth framework. 

#### Authentication Round 2
Using Google Sign In again meant we no longer needed the account creation and account log in flows, so those were removed. The `AccountManager` code was stripped from the project and new code that implemented the [AppAuth Android client](https://github.com/openid/AppAuth-Android) was added in. AppAuth abstracts away the authentication process behind an `AuthenticationService` and provides simple methods to handle authentication requests and fetch tokens. 

#### Search Functionality
Once auth tokens were able to be fetched I could move on to implementing new features. The next feature I added was the search feature. The backend returned paginated results for a search query. This was a perfect opportunity to use the new Android Jetpack Paging library. I followed the [Paging Library Codelab](https://codelabs.developers.google.com/codelabs/android-paging/index.html?index=..%2F..%2Findex#0) which was a perfect guide to implementing this feature. 


#### Sentiment Analysis
We defined a schema for sentiment analytics. At the moment only a few endpoints are implemented on the backend and I've started to build out a few of the graphs and widgets to display the data. You can see the design [here]({{ site.baseurl }}{% post_url  2018-11-17-fivethings %}#current-design).
