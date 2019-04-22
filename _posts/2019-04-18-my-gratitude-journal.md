---
layout: post
title:  "My Gratitude Journal: a Google Assistant Action"
date:   2019-04-18 20:45:31 +0530
categories: ["projects", "actions"]
---

On March 2nd, 2019 I was lucky enough to get into Women Techmaker's International Women's Day Summit. I had a great time meeting other women in the industry and got the opportunity to try out a Codelab for the Google Assistant. I zoomed through the Codelab and couldn't wait to get home to try to build one of my own, Google even gave everyone a free Google Home Mini to take home for practice! Thank you! 🙇‍♀️

Taking inspriation from [Presently]({{ site.baseurl }}{% post_url 2019-04-20-presently %}) I decided to build a gratitude journaling Assistant Action!

<img src="https://i.imgur.com/D8GRhdW.png">


### Tech Stack
I built my Action using the new [Java/Kotlin Actions on Google](https://github.com/actions-on-google/actions-on-google-java) library announced in January. This library is used for the fulfillment portion of my action, and I used the super convenient [boilerplate](https://github.com/actions-on-google/dialogflow-webhook-boilerplate-java) to start my project. My fulfillment code integrates my app with Firebase Cloudstore and Firebase authentication to allow users to store their entries securely.

The NLP is all handled with Dialogflow. In Dialogflow I created intents and added training phrases that parse user input and respond appropriately. 

### Challenges
Building the fulfillment code was the easiest part of this project thanks to the simplicity of the AoG Kotlin library and Firebase Cloudstore. Authentication was pretty straight forward and from then on all I had to do was read and write to my database, all of which is really well documented by Google.

The real challenge in building an Assistant Action is the Dialogflow portion. 

For one thing its very hard to guess what your <img align="right" height="350" src="https://i.imgur.com/28PVUGZ.gif" >users will really say to your Action.  Many times I would write out a new feature, test it myself, and not find any issues. It wasn't until I asked friends to try when I realized all the phrases I hadn't covered. This image is a snippet of the possible ways I've encountered to ask the Action to read an old entry to you. (and there's probably more I haven't seen!) Thankfully, Dialogflow has tooling to help you train your Action when users start talking to your Action.

The next hard thing for me to figure out was Dialogflow Context. Read the following conversation:

`USER: Write a new entry`

`ASSISTANT: What day would you like to write an entry for?`

`USER: Today`

`ASSISTANT: Okay, what are you grateful for today?`

`USER: I'm grateful for my best friend, Ellen`

At this point in the conversation my fulfillment code is invoked with the `ThingOfGratitude` passed along to me. But I need to know what date to write the entry for in my database. I can pass this information between Intents with Contexts. I define an outgoing Context when the user says "Today" and give it a lifespan long enough to reach the gratitude phrase. In my fulfillment code I use that context and add the given date to it. Then when I get to the gratitude phrase Intent I define the incoming Context as the same context with the date. 

My app had a lot of different Contexts to keep track of and it was very easy to get confused. Writing it all out on paper really helped me visualize the Contexts and find ways to optimize. Here's an example of one my visualizations:

<img src="https://i.imgur.com/JPyp109.jpg?2">

<br>
**The app is about to go to Beta pending a Google review, I'll update this post when it's available for testing!**