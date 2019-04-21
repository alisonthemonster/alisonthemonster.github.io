---
layout: post
title:  "Presently: A Gratitude Journal App"
date:   2019-04-20 19:45:31 +0530
categories: ["projects", "android"]
---
Presently is an open source Android app you can use to write down daily gratitude entries. Users can navigate through a simple timeline view and to add and read entries. It was designed to be very minimal, with no extra bells and whistles. I built this app to fill the void for simple gratitude journaling apps and to try out Room. I also wanted to try my hand at some design, from the app icon to the Play Store assets. 

### Features
  - Write and read gratitude journal entries
  - Export/import your entries to CSV 
  - Reminder notifications
  - [Coming soon] Themes

### Tech Stack
Presently is built using Android Architecture Components:
  - Room
  - Navigation
  - ViewModel
  - LiveData
  - Data binding
  
### Continuous Integration
  - CircleCI with Github integration
  - Fastlane to manage my CI tasks
       - A lane to run unit tests and generate coverage
       - A lane to run static code analysis
       - A lane to build the app
       - [Coming soon] A lane to release the app and perform release related tasks
   - Code coverage tracked using a [gradle task](https://github.com/alisonthemonster/Presently/blob/develop/app/jacoco.gradle) that would calculate my Jacoco coverage

### The Design
![Book templates](https://i.imgur.com/Hs6kxWi.png)


### Future Plans
  - Themes, various colors and symbols for users to chose from
  - Updated tooling for releases (using Fastlane and Gradle)
  - Use the Jetpack Paging library for the Timeline view
  - Search
  - Integrate Github with Danger to put code coverage reports in pull requests

Check it out here in the [Google Play Store](https://play.google.com/store/apps/details?id=journal.gratitude.com.gratitudejournal&hl=en)
 and look at my source code on [Github](https://github.com/alisonthemonster/Presently)!
