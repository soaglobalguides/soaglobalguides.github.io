---
layout: default
nav_order: 4
published: true
last_modified_at: 2021-08-14 00:00:00 +0000
---

# Sinoalice Global Tech Talk Summary
(Last updated August 14, 2021)

## Intro

The following is a list of points I found interesting in the [talk](https://www.youtube.com/watch?v=-fIBrXJOvtQ) given  on September 18, 2020 by Yasuyuki Kakuhari for the GREE Tech Conference 2020 about the Global version of Sinoalice. 

## Talk Intro

- Publishing rights handover from Nexon to Pokelabo happened around the end of 2019.

- Sinoalice wasn't originally developed with foreign editions in mind from an architecture or localization standpoint.

## Server-Related (PHP)

- Pokelabo wanted to partner with a foreign company for the release of global because of their poor track record of self-published global editions of games.

- Global pricing for different countries on App Store was easy due to the pricing tier system (same as in Japan). 

- Google pricing for different countries is much harder, because their pricing templates don't offer export/import features, sales tax causes prices to change, and prices need to match Apple.

- Asia server was in Singapore (ap-southeast-1), and US/EU was in Ohio (us-east-2). 

- They wanted to visit various countries before release to test connections, but couldn't due to Covid. Instead, they had outside companies assist them with the testing. 

- All translators were given Japanese text to work from.

- When Pokelabo took over from Nexon, the Global client was based off of Japanese version 29.2, while the version under development at the time was 59.0, about two years' worth of code difference that they began to address. 

- They used the time before release to make changes to code that they always wanted to add and improve bottlenecks they found on the domestic version.

- For server load tests, their calculations were based off of their current load against the traffic the game saw at release in Japan (1 million DAU). Their targets were 22,569 internal RPS and 31,801 external RPS.

- Some bottlenecks in JP Sinoalice that they addressed in Global include support for sharding (for character data) and denormalization of some data.

- RDS system load graphs for JP's Nier collab on 6/25 vs global's on 7/16:

JP:
![jp](https://i.imgur.com/XyXT3rj.png)
Global: 
![gl](https://i.imgur.com/CZCnlju.png)

## Client-Related (Unity)

- There was a conscious effort to make in-game times match the user's timezone (no UTC+0, etc). There was no common time-based logic in the game to begin with because it was originally designed with only Japan in mind, so they needed to find and address this in every unique instance. Had they had more development time, they probably would have made this into a common system. He thinks it's only a matter of time before this gets implemented, as they're constantly refactoring the code. 

- The client simply shows the correct language for each text field, meaning that there is no translation-related processing to be done on the server side. 

- They recognize there were times they missed a spot. 

![whoops](https://i.imgur.com/O78ySTA.png)

- However, because the in-game text is displayed based on downloaded files rather than the client itself, they were able to make quick fixes without having to pass the App Store / Google Play checks required for a new client version. 

![better than nothing](https://i.imgur.com/JlJ8MTv.png)

## Other

- At the end of the day, JP Sinoalice was their first priority. They couldn't allow Global development to cause issues with the domestic version, and only 3 employees were moved from the domestic team to work on Global (Kakuhari being one of them).

- Sinoalice JP uses .NET 3.5, but because Global was a new title, they could use .NET4.x.
