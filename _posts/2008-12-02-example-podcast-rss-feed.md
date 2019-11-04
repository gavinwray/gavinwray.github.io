---
title: "Example podcast RSS feed"
layout: post
categories: ["Content management", "Social media"]
tags: ["iTunes", "Podcast", "RSS", "XML"]
---

Last month, I submitted a podcast of conference speeches to the iTunes Music Store.

To do this, I had to make an RSS feed (an XML file) that:

- conformed to the [RSS 2.0 specification](http://cyber.law.harvard.edu/rss/rss.html)
- included the recommended iTunes RSS tags
- contained pointers to episodes

After reading tutorials and following [Apple's specification](https://help.apple.com/itc/podcasts_connect/#/itca5b22233a) I made my own RSS feed, filling it out with comments to refer to when updating the feed with future episodes. Hopefully, someone else will find this commented RSS feed useful.

As well as using this feed for submission to the iTunes Music Store, you can also share your podcast RSS feed for listeners to subscribe using their RSS reader.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!-- Define namespace for iTunes tags  -->
<rss xmlns:itunes="http://www.itunes.com/dtds/podcast-1.0.dtd" version="2.0">

<channel>
    <title>Your podcast series title</title>
    <link>http://www.mytopclasspodcasts.co.uk</link>
    <language>en-uk</language>
    <!-- Not visible in iTunes store -->
    <copyright>&#x2117; &amp; &#xA9; 2008 Your company name</copyright>
    <itunes:subtitle>A quick snappy description about your podcast series</itunes:subtitle>
    <itunes:author>Gavin Wray</itunes:author>
    <!-- Displayed in description column in iTunes. Keep this short. -->
    <itunes:summary>A summary of your podcast series. Look for our Podcast in the iTunes Music Store.</itunes:summary>
    <!-- Displayed when the 'i for info' icon in the iTunes' description column is clicked -->
    <description>Here you can use more characters to describe the content of your podcast series. Look for our Podcast in the iTunes Music Store.</description>
    <!-- Add name and email of the person administrating this podcat. The name and email is not displayed in itunes. Used for contact purposes only -->
    <itunes:owner>
        <itunes:name>Your first and last name</itunes:name>
        <itunes:email>anyname@mytopclasspodcasts.co.uk</itunes:email>
    </itunes:owner>
    <!-- Specify image to be used as iTunes artwork. Must be a .jpg or .png and at least 600x600 pixels -->
    <itunes:image href="http://www.mytopclasspodcasts/directory/directory/yourpodcastart.jpg" />
    <!-- Category and sub-category must be selected from iTunes' defined list -->
    <itunes:category text="Government &amp; Organizations">
        <!-- This is the sub-category from iTunes defined list -->
        <itunes:category text="Regional"/>
        </itunes:category>

    <!-- Use 1 item per episode -->
    <item>
        <title>Your first episode title</title>
        <!-- Shown in artist column in iTunes -->
        <itunes:author>My Top Class Podcast</itunes:author>
        <itunes:subtitle>This is subtitle of episode 1.</itunes:subtitle>
        <itunes:summary>This is the first episode of our new podcast on... In this episode we interview... etc.</itunes:summary>
        <!-- URL is the full path to your episode recording. The length attribute is the file size in bytes -->
        <enclosure url="http://www.mytopclasspodcasts.co.uk/podcasts/episode-1.mp3" length="258987" type="audio/mpeg" />
        <!-- Every item should have a globally unique identifier that never changes. When you add episodes to your feed, guids are compared in case sensitive fashion to determine which episodes are new. If you omit the guid for an episode, the episode url will be used instead. -->
        <guid>http://www.mytopclasspodcasts.co.uk/podcasts/archive/aaa-date.mp3</guid>
        <!-- Episodes in podcast are sorted by pubDate, most recent first. Note the timezone -->
        <pubDate>Mon, 1 Dec 2008 15:00:00 GMT</pubDate>
        <!-- Duration of the episode in minutes:seconds -->
        <itunes:duration>13:29</itunes:duration>
        <!-- Keywords are not visible but can be searched -->
        <itunes:keywords>podcasts, technology, interviews, etc.</itunes:keywords>
    </item>

    <!-- Repeat above item block for each subsequent episode -->
    <item>
        <title> </title>
        <itunes:author> </itunes:author>
        <itunes:subtitle> </itunes:subtitle>
        <itunes:summary> </itunes:summary>
        <enclosure url="http://www.mytopclasspodcasts.co.uk/podcasts/episode-2.mp3" length="123456" type="audio/mpeg" />
        <guid>http://www.mytopclasspodcasts.co.uk/podcasts/archive/aaa-date.mp3</guid>
        <pubDate>Monday, 8 Dec 2008 15:00:00 GMT</pubDate>
        <itunes:duration>12:58</itunes:duration>
        <!-- Keywords are not visible but can be searched -->
        <itunes:keywords>podcasts, technology, interviews, etc.</itunes:keywords>
    </item>

</channel>

</rss>
```
