# youtubeAnalyticsR
![](https://www.google.com/images/icons/product/youtube-32.png)
YouTube Analytics API R library

Retrieves your YouTube Analytics data.
This is an R package autogenerated via [googleAuthR](http://code.markedmondson.me/googleAuthR)'s Discovery API builder. 
The Google Documentation for this API is [here](http://developers.google.com/youtube/analytics/).

## Setup

1. Get a Google Project
2. Activate the YouTube API in your google project.
3. Get the OAuth2 client ID and secret (see GoogleAuthR readme for details)
4. Set options `options(googleAuthR.client_id = XXX)` and `options(googleAuthR.client_secret = )`
5. Load the library
6. Run `yt_auth()` and authenticate with your user
7. Run `yt_analytics()` to get data

Work in progress, and requests please file a Github issue. 

```r
options(googleAuthR.client_id = XXX)
options(googleAuthR.client_secret = XXX)

library(youtubeAnalyticsR)

## authenticate with a user who has access to the YouTube channel you want to analyse
yt_auth()

## get the unique ID of your YouTube Channel
ya <- yt_analytics("UCvcKAjtJAzVr0vgLNR5w7Fg", 
                  start.date = "2016-09-01", end.date = "2016-10-01", 
                  metrics = "views", dimensions = "day")
ya
#          day views
#1  2016-09-23   489
#2  2016-09-26   391
#3  2016-09-13 29810
#4  2016-09-18   442
#.   ....        ...
```
