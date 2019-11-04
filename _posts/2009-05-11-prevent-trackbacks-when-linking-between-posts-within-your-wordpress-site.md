---
title: "Prevent trackbacks when linking between posts within your WordPress site"
layout: post
categories: ["Content management", "WordPress"]
tags: ["Blogging", "Linking", "Trackbacks", "WordPress"]
---

I'm a fan of revisiting posts within a blog and linking to related posts. Whether adding cross-references in the body of the text or at the end of a post via a [related posts plugin](http://wordpress.org/extend/plugins/search.php?q=related+posts), I think these links can benefit both readers and site owners.

Linking between posts is also essential if you're writing a series of related posts.

One result of linking posts bothers me though. Trackbacks or pingbacks in the comments section of your own post don't make sense in the context of your own site. Trackbacks only make sense in the context of other people linking to your post.

So how do trackbacks appear in the first place?

In WordPress, if you've enabled trackbacks and pingbacks in your post:

![Trackbacks and pingbacks enabled in WordPress](/assets/2009/05/trackbacks-pingbacks-enabled.png)

and you add an absolute link to a second post within your site:

![Insert link dialog box in WordPress admin interface](/assets/2009/05/insert-link-dialog-box.png)

a trackback appears in the comments list of the second post.

## How to prevent trackbacks for posts within your own site

You can prevent trackbacks appearing when linking posts on your own site by using relative instead of absolute links. For example, use the relative link:

``` html
/link-to-post
```

instead of the absolute link:

``` html
http://yoursite.com/link-to-post
```

[Hat tip to Tim J](http://twitter.com/timtfj/statuses/1648310438) for this information.
