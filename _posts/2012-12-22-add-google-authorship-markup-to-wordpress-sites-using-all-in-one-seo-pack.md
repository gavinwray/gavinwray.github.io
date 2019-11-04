---
title: "Add Google authorship markup to WordPress sites using All in One SEO Pack"
layout: post
categories: ["Content management", "WordPress"]
tags: ["Authorship", "Google", "HTML", "Metadata", "Rich snippets", "SEO", "Structured data", "WordPress"]
---

_Updated 28 August 2014: John Mueller of Google Webmaster Tools [announced](https://plus.google.com/+JohnMueller/posts/HZf3KDP1Dm8) that Google will stop showing authorship results in Google Search._

- - - -

I've read up on [Google authorship markup](http://googlewebmastercentral.blogspot.co.uk/2011/06/authorship-markup-and-web-search.html) this week, particularly in the context of adding it to self-hosted WordPress sites.

For Google, the idea is to surface popular authors' web content in search results. For writers or anyone publishing online, you can assert ownership of your content and enhance your personal brand online. (Urgh, I sound like a snake oil marcomms consultant in that last sentence; it's true though.)

Google shows the author's avatar and extra detail in search results, which help the author's content stand out. For example:

![Authors in Google search results with photos](/assets/2012/12/authors-in-google-search-results.png)

Authorship markup describes the relationship between a piece of content and its author semantically. This helps search engines to identify the author's work wherever it appears online. In practice, this means explicitly linking your Google+ profile to your content using `rel="author"`.

## Connect your sites to your Google+ profile

The first thing to do is add the sites you write for to your Google+ profile:

1. In Google+, go to your profile and click **Edit profile**.

2. Click the **About** tab and scroll down to the **Contributor to** section.

3. Click the **Contributor to** label and add your website.

    ![Contributor to site URLs](/assets/2012/12/contributor-to1.jpg)

4. Save your changes.

## Add authorship markup to a single-author WordPress site

After reading lengthy guides by [Rick DeJarnette](http://searchengineland.com/the-definitive-guide-to-google-authorship-markup-123218) and [Tara Horner](http://designfestival.com/add-rich-snippet-support-in-wordpress-and-dominate-your-personal-brand/), adding authorship markup seems too complex a process. For WordPress themes, Tara explains editing the post and author page templates to include `rel="author"` on the post author name anchor, and linking the author's name to her Google+ profile.

This doesn't suit my purposes.

Firstly, I'm the only person writing on this site. This is a ‘single-author WordPress blog’ and it's obvious to readers I write all the posts. To change the post metadata to include my name, and link it to my Google+ profile, just so I can add `rel="author"` seems daft. That would mean changing the post metadata from:

```html
Carefully posted on 15th December 2012
```

...to:

```html
Carefully posted on 15th December 2012 by <a rel="author" href="https://plus.google.com/u/1/109382002866848246485/">Gavin Wray</a>
```

For multi-author WordPress blogs, changing the post metadata in this way would break WordPress' established navigation to view all posts by an author by clicking the author's name.

After digging around my site, I found a solution using the [All in One SEO Pack](http://wordpress.org/extend/plugins/all-in-one-seo-pack/) plugin.

1. In your WordPress dashboard, go to **Settings > All in One SEO**.

2. Scroll down to the text field labelled **Google Plus Profile Sitewide Default** and enter your Google+ profile URL. If you don't know your URL, go to [Google+](https://plus.google.com), right-click on your **Profile** icon and copy the link. It looks something like:

    ```html
    https://plus.google.com/u/1/1234567890
    ```

    ![Copy Google+ profile URL](/assets/2012/12/copy-google-profile-url.png)

3. Scroll to the bottom of the All in One SEO settings and click **Update Options**.

4. Visit any page on your website and view the source HTML. Notice the following line in the `head` section:

    ```html
    <link rel="author" href="https://plus.google.com/u/1/109382002866848246485" />
    ```

    This line tells search engines that the page was written by the person who owns the Google+ profile at the specified URL.

5. Now it's time to test using Google's [structured data testing tool](http://www.google.com/webmasters/tools/richsnippets) tool. Copy any URL of a page on your site and paste it in the URL field. You should see a preview of how your page will appear in search results alongside your avatar, links to more of your content and verified authorship:

    ![Authorship preview in Google structured data testing tool](/assets/2012/12/authorship-preview-in-structured-data-testing-tool.png)

## Add authorship markup to a multi-author WordPress site

If your WordPress site has multiple contributors and you're using the All in One SEO Pack, the process to add authorship markup is different.

1. In your WordPress dashboard, go to **Settings > All in One SEO**.

2. Scroll down to the text field labelled **Google Plus Profile Sitewide Default** and ensure it's empty.

3. Go to **Users > Your Profile** and you can see a field labelled **Google+**.

4. Enter your Google+ profile URL and save your changes.

5. Visit any post or page _that you published on the site_, view the source HTML and you should see the markup in the `<head>`:

    ```html
    <link rel="author" href="https://plus.google.com/u/1/109382002866848246485" />
    ```

I hope this method is simpler than editing your WordPress theme.
