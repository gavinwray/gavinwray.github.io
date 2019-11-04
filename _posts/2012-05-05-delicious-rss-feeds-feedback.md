---
title: "Delicious RSS feeds feedback"
layout: post
categories: ["Content management"]
tags: ["Delicious", "RSS", "Social bookmarking", "Tagging"]
---

Updated 14 November 2012: the solution to get an RSS feed for a generic tag (not a tag by Delicious user) in this post no longer works. Thanks [Judith Townend](http://twitter.com/JTownend/status/268741081234038784) for mentioning it.

---

Much of my job at [Podnosh](http://podnosh.com) involves training people to use social media to communicate and collaborate more efficiently.

A few weeks ago, [Steph Jennings](https://twitter.com/essitam) and I worked with a group from the [Fair Brum](http://fairbrum.wordpress.com/) Social Inclusion Process. At one point, I was demonstrating how social bookmarks could be useful, using [Delicious](http://delicious.com/) as an example, particularly from the perspective of gathering research, curation and sharing within teams.

The idea is that if one person in your team is doing desk research, gathering links, filtering and sorting, then the individual's effort involved in doing that work is magnified by a small, additional effort - sharing. One way to do this is for the person doing the research to use social bookmarking to tag and arrange the links, which other people in the team can subscribe to via [RSS](http://www.commoncraft.com/video/rss).

One person asked:

> "Do we all need Delicious accounts to see other people's bookmarks?"

I replied something like:

> “No, you don't need an account. In fact, if someone in your team is already gathering links to research and useful online sources, if she consistently tags her bookmarks &ndash; for example, using the [fairbrum](http://delicious.com/tag/fairbrum) tag &ndash; you can subscribe to their bookmarks via RSS.”

And then, demonstrating this to the group on the projector, I came unstuck. View a tag on Delicious, for example: [http://delicious.com/tag/fairbrum](http://delicious.com/tag/fairbrum). Ahem, there is no RSS feed for the tag:

![Missing RSS feed on delicious.com when viewing a tag](/assets/2012/05/where-is-rss-feed.png)

This was embarrassing. It also confused me, as I was sure you could subscribe to an RSS feed of pretty much anything in Delicious.

I searched and tweaked of the URL by hand. It turns out that you can subscribe to an RSS feed for any new bookmarks with a common tag. You just need to enter the URL by hand in your web browser's address bar. For example, this gives you a feed of all bookmarks tagged `fairbrum`:

```html
http://feeds.delicious.com/v2/rss/tag/fairbrum
```

If you want a feed of bookmarks with a different tag, swap the tag at the end of the feed URL. For example, to get an RSS feed of bookmarks tagged `birminghamuk` use:

```html
http://feeds.delicious.com/v2/rss/tag/birminghamuk
```

It works but it's a bit of a faff. I'd like to see an RSS feed available for any public page I happen to be viewing on Delicious: user, tag, combinations of tags, a stack or search. That would be useful.

I let [Delicious](http://twitter.com/#!/delicious) know via Twitter. I hope they implement my feedback.
