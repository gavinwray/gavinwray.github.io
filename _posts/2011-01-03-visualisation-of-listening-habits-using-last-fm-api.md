---
title: "Visualisation of listening habits using last.fm API and Google Spreadsheets"
layout: post
categories: ["Content design", "Open data"]
tags: ["Data", "Design", "Google Spreadsheets", "Infographics", "Last.fm", "Music", "Scrobbling", "Visualisation"]
---

I've made a data visualisation showing the top 50 artists I listened to in 2010. The size of the artist photo is proportional to the number of times I listened to any track by that artist in 2010. This post walks you through my process to create the image.

![Visualisation of top 50 listened to artists in 2010](/assets/2011/01/my-top-artists-2010-viz-final.jpg)

## Overview

1. Get the listening data from the last.fm API.
2. Turn the data into a form suitable for importing into Google Spreadsheets.
3. Visualise the data in a tree map.
4. Overlay the photos on the tree map.

## Get the listening data from last.fm API

I use [Last.fm](http://last.fm) to store data about my listening habits. Any track I listen to on my phone, in Spotify or the last.fm website is &lsquo;scrobbled&rsquo; to [my Last.fm profile](http://www.last.fm/user/denituthered).

You can access your data using the [Last.fm API](http://www.last.fm/api).  (Sign up for an API key, if you haven't already done so.) You get the data by submitting a request (i.e. typing the address in a web browser) to:

```html
http://ws.audioscrobbler.com/2.0/
```

&hellip;and appending a method, your API key and (optionally) a time period.

To get the data about the top artists I listened to in 2010, I used `getTopArtists`:

```html
http://ws.audioscrobbler.com/2.0/?method=user.gettopartists
&amp;user=denituthered&amp;period=12month&amp;api_key=myAPIKey
```

This returns the data as XML. It looks something like this:

```xml
<lfm status="ok">

  Left Lane Cruiser
  179

  http://www.last.fm/music/Left+Lane+Cruiser
  1
  http://userserve-ak.last.fm/serve/34/13235587.jpg
  http://userserve-ak.last.fm/serve/64/13235587.jpg
  http://userserve-ak.last.fm/serve/126/13235587.jpg
  http://userserve-ak.last.fm/serve/252/13235587.jpg
  http://userserve-ak.last.fm/serve/500/13235587/Left+Lane+Cruiser+LLC.jpg

  Otis Taylor
  165
  ...

  Black Stone Cherry
  165
  ...
```

## Prepare the data for Google Spreadsheets

I wanted my data in Google Spreadsheets so I could use Google's visualisation tools. However, XML isn't a supported file format, so I couldn't just throw my XML file up there and start. I needed to turn my XML into a format suitable for Google Spreadsheets, such as CSV.

You can do this with recent versions of Microsoft Excel or other Office tools. I needed something free and used [Google Refine](http://code.google.com/p/google-refine/). It's useful for cleaning data and exporting to different formats.

I opened the XML file in Google Refine and deleted the extraneous columns and rows, leaving the following fields (as column titles):

* Rank
* Artist
* Playcount
* Image URL

I then saved the data as a CSV file and uploaded it to Google Spreadsheets ([see the file](https://spreadsheets.google.com/ccc?key=0AgZ8vzDVpgaQdDlpd05mVFFEYkhsUnUtQTQwSWJWbnc&hl=en_GB)).

## Visualise the data

To get the basic layout of the visualisation I created a tree map. In Google Spreadsheets:

1. I selected the required data fields: `Artist` and `Playcount`.
2. Chose **Insert > Gadget > Tree Map Gadget**.
3. Placed the tree map in a new sheet.

![Top 50 listened to artists visualised as a treemap](/assets/2011/01/treemap-fullsize.png)

The tree map recalculates itself when you change your browser window dimensions. I wanted to make an image at approximately A4 landscape, and changed the window dimensions until I got a layout that felt right.

## Overlay the photos

I took a screenshot of the tree map, opened it in an image editor and increased the image dimensions by 50% to create a larger image to work with.

The Last.fm data includes image URLs. I did use some, but where there were odd shapes in the tree map, I searched for suitable images that work well in extreme letterbox or elongated shapes.

The final stage involved cropping the photo of each artist to the same dimensions as the underlying shape in the tree map. I started with Left Lane Cruiser and Otis Taylor at the top left, then worked my way through the other artists.

![Overlay photos on tree map](/assets/2011/01/overlay-photos.jpg)

This is the final result:

![Visualisation of top 50 listened to artists in 2010](/assets/2011/01/my-top-artists-2010-viz-final.jpg)
