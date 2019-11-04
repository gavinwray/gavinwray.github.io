---
title: "Migrating 'The Perfect Twang' from WordPress to Hugo"
layout: post
categories: ["Content management", "Hugo", "Process", "WordPress"]
tags: ["Content management", "Hugo", "Learning", "Static site generator", "WordPress"]
---

Learning a blog platform other than WordPress has been on my mind for a while. I've worked with WordPress sites as an author, editor or general maintenance man for ten years now. It's time to try something new.

I researched static site generators and chose to learn [Hugo](https://gohugo.io/). Aside from learning a new technology, another reason for moving the blog to a static site generator is that my WordPress sites are so slow.

After a steep learning curve, I migrated my music blog [The Perfect Twang](https://twang.city) from WordPress to Hugo. [Edited 6 October 2019: this blog is now on [WordPress.com](https://perfecttwang.wordpress.com/).]

This post summarises what I've learned so far. For more detailed guides, try reading:

* [switching from WordPress to Hugo](http://justinfx.com/2015/11/08/switching-from-wordpress-to-hugo/) by Justin Israel
* [migrating from WordPress to Hugo](http://justindunham.net/migrating-from-wordpress-to-hugo/) by Justin Dunham

## Installation and set-up

Installing Hugo on my Mac was the most difficult part of the migration. This is mainly due to my lack of skills with a command line and Mac permissions! While the Hugo installation instructions are short and clear, I hit permissions problems in Terminal, which took some research to figure out.

Once I resolved these niggles, I found it straightforward to get a vanilla site up and running. Win!

## Content review

I used Ben Balter's [WordPress to Jekyll plugin](https://wordpress.org/plugins/jekyll-exporter/) to export my blog posts as Markdown files, which contained tags, categories and other metadata. The export includes a copy of the `/wp-content` folder, which contains images or other uploads related to posts and pages.

Reviewing the content is where I spent the bulk of my time. This involved:

* fixing instances in Markdown files where symbols had changed to HTML entities, such as apostrophes or quotation marks
* replacing absolute image paths containing WordPress' `/wp-content/uploads/etc` to be relative to Hugo's `/static` directory
* understanding where to store images and other media files referenced by posts. (There's extensive discussion on [GitHub](https://github.com/spf13/hugo/issues/147).) I settled on recreating WordPress' uploads structure of `/year/month/myimage.jpg` under my Hugo site's `/static/media` directory
* understanding how to recreate WordPress' permalink structure via Hugo's config settings to avoid having to implement any URL redirection or risk losing PageRank

## Theme and design

There are plenty of [themes](http://themes.gohugo.io/) available for Hugo sites. I chose the [Icarus](https://github.com/digitalcraftsman/hugo-icarus-theme) theme by [Zhang Ruipeng](http://github.com/ppoffice) and [Digitalcraftsman](https://github.com/digitalcraftsman) for two reasons:

* you can include featured images with posts (known as 'banners' in Icarus)
* there's a consistent-looking archives page that includes featured images

I customised the theme with an override stylesheet to improve the following aspects:

* contrast in the typography to meet [WCAG](https://www.w3.org/TR/WCAG20/) level AA.
* navigation on small screens, particularly at 400px wide
* post titles in archive pages on small screens

There's still work to do to be fully compliant with WCAG level AA but the major elements now pass.

## Deploy

When the site is ready on your local computer, you type `hugo` in the command line to generate all the site files in the `/public` directory. You then upload the `/public` directory to the web server.

When you write a new post, you need to regenerate the site and upload the entire directory of site files to your web server. My Perfect Twang blog of 20-something posts is 11 MB when compiled in Hugo. Via my Virgin Media broadband connection, this takes about 20 minutes to upload via FTP to DreamHost. Already, uploading by FTP has become a timesink, particularly when making small changes such as fixing a typo or publishing a new post.

Next on my Hugo to-do list is to find a more efficient way to track and deploy changes to the live web server.

## Performance

I'm happy with Hugo in this area. With no queries or round trip to a database like WordPress requires (Hugo sites are simple, static html pages) there's a significant improvement.

The following table compares performance of the home page before and after the move to Hugo:

<table id="" summary="Comparison of home page performance between WordPress and Hugo">
<thead>
<tr>
<th style="text-align: left;" scope="col">Measurement</th>
<th style="text-align: right;" scope="col">Before (WordPress)</th>
<th style="text-align: right;" scope="col">After (Hugo)</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align: left;">Load time</td>
<td style="text-align: right;">1.33s</td>
<td style="text-align: right;">703ms</td>
</tr>
<tr>
<td style="text-align: left;">Requests</td>
<td style="text-align: right;">65</td>
<td style="text-align: right;">28</td>
</tr>
<tr>
<td style="text-align: left;">Pingdom performance grade</td>
<td style="text-align: right;">69/100</td>
<td style="text-align: right;">86/100</td>
</tr>
<tr>
<td style="text-align: left;">Page size</td>
<td style="text-align: right;">1.2mb</td>
<td style="text-align: right;">727kb</td>
</tr>
<tr>
<td style="text-align: left;">YSlow grade</td>
<td style="text-align: right;">C</td>
<td style="text-align: right;">B</td>
</tr>
<tr>
<td style="text-align: left;">YSlow performance score</td>
<td style="text-align: right;">78</td>
<td style="text-align: right;">82</td>
</tr>
</tbody>
</table>
