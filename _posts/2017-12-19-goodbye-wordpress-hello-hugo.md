---
title: "Goodbye WordPress, hello Hugo"
layout: post
categories: ["Hugo", "News"]
tags: ["Blogging", "Hugo", "Static site generator"]
---

After nine years on a self-hosted [WordPress](https://wordpress.org/) platform, I’m now running this site on [Hugo](https://gohugo.io/), an open-source static site generator. I migrated the blog posts and static pages, removed obsolete material, and updated the post categories.

I dropped featured images from blog posts, mainly to save time in the content migration, so the site does look, well, minimal. Colour and imagery may return in the future but I'm happy with the stark feel for now. The off-black and off-white palette is a deliberate aesthetic but also an active choice to remove as much visual clutter and functionality as possible.

The theme is [Future Imperfect](https://html5up.net/future-imperfect), [ported to Hugo](https://themes.gohugo.io/theme/future-imperfect/) by [Julio Pescador](https://github.com/jpescador). I added a custom stylesheet to:

* increase the colour contrast and font size for accessibility - a [Lighthouse](https://developers.google.com/web/tools/lighthouse/) audit reports an increase in the accessibility score from 89 to 94
* constrain the main content on screen widths between 980 and 1,280 pixels to maintain a readable line length

One reason why I left WordPress was the amount of time I spent keeping the lights on when I should have been writing instead. Even after rationalising plugins, caching content and reducing backups to one per week rather than daily, I often hit my shared hosting plan's process watcher. That caused the site to time out.

Positively though, I wanted to try another platform to learn something new and to practice maintaining a site through modern processes. At [work](https://warwick.ac.uk/its/servicessupport/web) this year, I started contributing user interface copy to a web app via a [Git workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow). I've also been reading articles by other technical writers in the [Write the Docs](http://www.writethedocs.org/) community, particularly the [docs as code](http://www.writethedocs.org/guide/docs-as-code/) movement.

This personal Hugo site gives me the opportunity to:

* get in the habit of writing and editing with Markdown
* practice making changes via version control with the [Sourcetree app](https://www.sourcetreeapp.com/) and a [Bitbucket](https://bitbucket.org/) repository

Also, the act of writing in a text editor is a welcome return to a more deliberate approach. I'm more in control of the tools, the published output and the visual form. It feels like cultivating a craft, which is a happy state to be in.
