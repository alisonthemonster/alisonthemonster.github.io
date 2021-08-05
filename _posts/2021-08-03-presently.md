---
layout: post
title:  "Presently: 2021 Update"
date:   2021-08-03 19:45:31 +0530
categories: ["projects", "android", "presently"]
---
It's been over a year since my last update on Presently and a lot has happened! Presently has hit half a million downloads, you can automatically back up your entries to Dropbox, modularization of the code base, sharing improvements and more. 


## Sharing your gratitude
Our previous sharing feature just allowed our users to share the text of their gratitude entry. We noticed that users were frequently sharing screenshots of their entries and thought we could help our users better share their gratitude. Now users can share a generated image of their gratitude.

## Automatic Dropbox Backups
We've had a CSV export and import feature since our very early days, but users had to manually backup their data to their device. Now users can connect their Dropbox accounts to the Presently app and have their entries automatically exported to their Dropbox account. Under the hood we're using WorkManager and the Dropbox Java SDK to upload their entries. 

## More customization options
Some great open source contributions and user feature requests now let our users really customize Presently. Users can now chose how long their entries are in the timeline, to display the day of the week, and can pick from over 25 different themes.


## Architecture and Technical Improvements
Since the last update I've really tried to focus on modernizing the codebase and improving app quality. Big improvments have been made around testing, architecture, and modularization.

### Architecture
When I started learning Flutter I played around with BLoC and got my first exposure to an MVI architecture. I really enjoyed it and had looked forward to using Airbnb's Mavericks framework. I've so far refactored the gratitude entry screen and written a new feature, sharing, using Mavericks. 

### Modularization + DI
Previously all Presently code was found in the `app` module, and while the app is relatively small there was definitely room for improvement. Now we have modules for common UI elements, new features, testing utilities, logging, and settings. Modularizing the code base meant big changes had to be made to our CI system and code coverage reporting. Because of this we started using Fladle to run all of the various instrumented tests across modules.

Presently also switched over to using Hilt. This simplified our existing Dagger usage and helped us write better UI tests! We also are now actively wrapping third party code to help us easily swap out implementations for testing or experimentation. 


Check it out here in the [Google Play Store](https://play.google.com/store/apps/details?id=journal.gratitude.com.gratitudejournal&hl=en)
 and look at my source code on [Github](https://github.com/alisonthemonster/Presently)!
