---
title: "Self-hosted WordPress housekeeping"
layout: post
categories: ["WordPress"]
tags: ["Optimisation", "WordPress"]
---

After nearly a year of neglect, I've cleaned up this site behind the scenes. There are no visible changes to the design but the content now loads faster.

Here are my notes on improvements to aid my own memory so I can repeat the steps on other self-hosted installations. If you're considering optimising your own WordPress site, I recommend that you back up everything and read these posts on _Smashing Magazine_:

- [How to speed up WordPress](http://www.smashingmagazine.com/2014/06/25/how-to-speed-up-your-wordpress-website/#more-191689)
- [WordPress performance improvements that can go wrong](http://www.smashingmagazine.com/2014/03/21/wordpress-performance-improvements-that-can-go-wrong/)

Also, please don't take my word that these steps are the 'correct' way. I'm no expert.

## 1. Back up everything

I use the [BackUpWordPress](https://bwp.hmn.md/) plugin by Janis Elsts to save a ZIP file that contains the database and site files. If things go pear-shaped, I can rebuild the site from scratch with this ZIP.

## 2. Delete redundant plugins

Active and inactive plugins can build up over time. It's worth reviewing your plugins to check if you still need them. I discovered that the [All in One SEO](https://wordpress.org/plugins/all-in-one-seo-pack/) plugin can generate an [XML sitemap](https://support.google.com/webmasters/answer/156184?hl=en). Bye bye to a standalone sitemap generator plugin.

Also, updates to the WordPress core can render some plugins obsolete. For example, embedding video URLs is much nicer in [version 4.0](http://www.smashingmagazine.com/2014/08/27/a-tour-of-wordpress-4-0/). Maybe you no longer need those social embed plugins.

## 3. Disable unused features in Jetpack

[Jetpack](https://wordpress.org/plugins/jetpack/) is a huge plugin with functionality that's default in WordPress.com-hosted sites. I find [After the Deadline,](http://wordpress.org/extend/plugins/after-the-deadline/) the ability to write in Markdown, tiled image galleries and [Photon CDN](http://jetpack.me/support/photon/) useful.

You may have more Jetpack features enabled than you need, want or use though. In your dashboard, go to **Jetpack > Settings** and select **Active**. Hover over any features you do not need and select **Deactivate**:

![Jetpack active modules](/assets/2014/10/jetpack-active-modules1.png)

## 4. Optimise the database

I use [WP-Optimize](https://wordpress.org/plugins/wp-optimize/) to reduce the size of my database. This removes a lot of crud such as old post revisions. It reduces the database size by about a third.

## 5. Caching

This is a strange one. I don't get on with caching plugins. I've tried [WP Super Cache](https://wordpress.org/plugins/wp-super-cache/) and [W3 Total Cache](https://wordpress.org/plugins/w3-total-cache/). Neither result in the performance boost I hope for.

I deleted the caching plugins and found a setting in the Wordfence plugin: **Wordfence > Performance setup > Enable basic caching**.

That's it for now. While this site is not what you'd call swift, there is an improvement. Now it's time to start writing posts instead of fettling behind the scenes.
