---
title: "I've been hacked"
layout: post
categories: ["News"]
tags: ["Hacked", "Hosting", "News", "Security", "WordFence", "WordPress"]
---

This site was hacked in early January. The first I knew of the hack was seeing the words “This site may be compromised” in Google's search results and my page titles filled with spam.

More than two weeks later, some of my pages (particularly tag archives) in Google's index are still affected:

![Google search results for my site on 24th Jan 2013](/assets/2013/01/google-results.png)

It's a sickening feeling knowing your public words, a good chunk of your online heritage, have been wrecked. It's more frustrating to know that the hack was unlikely deliberate or personal. A vulnerability in my WordPress installation or settings allowed a machine to probe, enter and frack about with my site.

If you've ever had your WordPress site hacked, you'll recognise that plunging feeling in your stomach as you see upcoming free evenings and weekends vanish. You know your time will disappear in the screen glare of tutorials, how-to guides, exporting and importing databases, phpMyAdmin and support calls with your web host.

Since then, I've decided to start over with a new WordPress install and the [Pinboard](http://www.onedesigns.com/wordpress-themes/pinboard) theme ~~you can see now~~.

Eventually technology forced my hand. After crafting a new local version of this site using [MAMP](http://www.mamp.info/en/index.html) and [WordPress](http://wordpress.org), deploying the database to the live site proved beyond me.

The method I've used before -- export your local database, find all instances of `yourtest.yourdomain.com` and replace with `yourdomain.com`, save and upload to your live site along with the new `wp-content` directory -- didn't work. Rolling back to an earlier version of the live site didn't work either. Mysteriously, I was left with a home page but no blog. Papsticks.

In a fit, I trashed the lot, created a fresh install on the live domain name, used WordPress' import/export tool to import content from my Mac into the site you can see now. This means that all the posts and pages are back, though many images are missing from the content and there are no featured images on posts yet.

I apologise now if you follow links that don't work or read a how-to post with screenshots missing. It'll take a few days for me to get things back in order.

In the meantime, here are some tools and mentions of people who proved invaluable in restoring this site and making it more secure:

* My web host [DreamHost](http://dreamhost.com/) were fantastic, giving me detailed step-by-step instructions on clearing up my server and working through my WordPress install to check for anomalies or malicious changes.
* [James Clarke](http://www.jamesdclarke.com/) recommended [Sucuri SiteCheck](https://sitecheck.sucuri.net/), a tool to scan your site for malware. Even better, James recommended the [WordFence](http://wordpress.org/extend/plugins/wordfence/) plugin. This has been a real eye-opener. As well as containing tweaks to shore up vulnerable areas bots and hackers look for, you can use it to automatically block bots that hammer your WordPress login page and get email alerts. I've just checked my email. In the last hour, there have been 33 different instances of a bot attempting to log in to my WordPress dashboard. Yikes!
* A post on [how to remove this site may be compromised warning](http://www.wpsite.net/how-to-remove-this-site-may-be-compromised-warning/) by Charlie Patel.
* Advice on [cleaning your site](http://support.google.com/webmasters/bin/answer.py?hl=en&answer=163634&topic=2365140&ctx=topic) in Google Webmaster Tools. [Updated 13th March 2013: Google announced new [resources for hacked site recovery](http://googlewebmastercentral.blogspot.co.uk/2013/03/new-first-stop-for-hacked-site-recovery.html).]
