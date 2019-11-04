---
title: "Reusable blockquote markup in WordPress using post snippets"
layout: post
categories: ["Content design", "WordPress"]
tags: ["A List Apart", "Blockquote", "HTML", "Tim Murtaugh", "Typography", "Web standards", "WordPress"]
---

_9 February 2013: The instructions in this post to implement the blockquote markup using the Post Snippets plugin for WordPress are accurate. However, the markup itself has been updated. See the [updated blockquote post snippet](/2013/12/updated-blockquote-post-snippet-for-wordpress/) for the improved markup._

---

Two posts I found useful this week are:

* A List Apart's [official blockquote patterns](http://alistapart.com/blog/post/more-thoughts-about-blockquotes-than-are-strictly-required) by Tim Murtaugh
* [How to improve your writing in WordPress](http://www.webdesignerdepot.com/2013/01/how-to-improve-your-writing-in-wordpress/) by Anna Ladoshkina

I was looking for sample blockquote markup with scope for including author names, citations and source URLs in a way that visually makes sense to readers, yet is semantically correct in HTML5.

[Tim Murtaugh](http://monkeydo.biz/), working on the HTML5 templates for _A List Apart_, shared his [thinking on marking up blockquotes](http://alistapart.com/blog/post/more-thoughts-about-blockquotes-than-are-strictly-required) and posted the code on [GitHub](https://gist.github.com/4489740).

I've copied Tim's markup for a single line blockquote with attribution and optional cite below, and added an optional URL to the cite text, as this is what I'll use to create a snippet in WordPress:

```html
<figure class="quote">
  <blockquote>The quote text goes here.</blockquote>
  <figcaption>Author name, <cite><a href="#">Cite the source title with optional URL</a></cite></figcaption>
</figure>
```

The blockquote renders like this:

> The quote text goes here.

In Tim's markup, `<figure>` has the class `quote`, which you can use as a hook to style the `<figure>` container. I used the following CSS to style the quote, indent the attribution and insert an em dash before the author name, purely for aesthetic purposes:

```css
.quote figcaption {
  font-size: .85em;
  margin-left: 60px;
}
.quote figcaption:before {
  content: "\2014 \2009";
}
```

Now I know the correct markup, I'll reuse it.

## Save blockquote markup using Post Snippets plugin

I could save the markup in a text file and cut and paste it into a draft WordPress post. This is messy though. Inevitably, I'll have to swap between the visual and text editors to get it right, and that's a faff.

I installed the [Post Snippets plugin](http://wordpress.org/extend/plugins/post-snippets/), which I found via Anna Ladoshkina's post on [how to improve your writing in WordPress](http://www.webdesignerdepot.com/2013/01/how-to-improve-your-writing-in-wordpress/).

You can use the plugin to save snippets of text, HTML or other code for reuse, which you access via the toolbar in WordPress' visual editor.

Here are the steps to make a reusable blockquote snippet.

1. Download and install the [Post Snippets plugin](http://wordpress.org/extend/plugins/post-snippets/), then activate it.

2. In your WordPress dashboard, go to **Settings > Post Snippets**.

3. Choose **Add New Snippet**.

    ![Add new post snippet fields](/assets/2013/02/add-new-snippet.png)

4. In the **Title** field, type:

    ```txt
    Blockquote
    ```

5. In the **Variables** field enter:

    ```txt
    quote,author,sourcetitle,sourceurl
    ```

6. In the **Snippet** field enter the following `<blockquote>` markup, noting the variables' location:

    ```html
    <figure class="quote">
      <blockquote>{quote}</blockquote>
      <figcaption>{author}, <cite><a href="{sourceurl}">{sourcetitle}</a></cite></figcaption>
    </figure>
    ```

7. In the **Description** field, enter a suitable description for your snippet. This helps you find it again in the visual editor. I used **Single line blockquote with attribution and cite including source URL**.

8. Leave everything else unselected and click the **Update Snippets** button.

## Insert post snippets using the visual editor

1. Start a draft post and you should see a new icon on the toolbar:

    ![New icon on toolbar to insert post snippet](/assets/2013/02/insert-post-snippet-icon.png)

2. Click the icon and you get a **Post Snippets** pop-up:

    ![Insert post snippets popup box with text fields to enter quote, author, source title and source url](/assets/2013/02/insert-post-snippet-popup.png)

3. Add your content into the four fields. For example, to quote from Tim's post, I enter the following:

    * **quote**: “So, here they are, [the official ALA blockquote patterns](https://gist.github.com/4489740). A lot of thought for what might be a small detail, but in thinking about these things now we’re doing our best to make sure that our content is future-friendly, and not just our templates.”
    * **author**: Tim Murtaugh
    * **sourcetitle**: A List Apart    
    * **sourceurl**: http://alistapart.com/blog/post/more-thoughts-about-blockquotes-than-are-strictly-required

4. When you have added your content, click **Insert**. You should see your blockquote and the four different content items marked up correctly. Here is my blockquote code:

    ```html
    <figure class="quote">
      <blockquote>So, here they are, the <a href="https://gist.github.com/4489740">official ALA blockquote patterns</a>. A lot of thought for what might be a small detail, but in thinking about these things now we’re doing our best to ensure that our content is future-friendly, and not just our templates.</blockquote>
      <figcaption>Tim Murtaugh, <cite><a href="http://alistapart.com/blog/post/more-thoughts-about-blockquotes-than-are-strictly-required">A List Apart</a></cite></figcaption>
    </figure>
    ```

## Final thoughts

This will save me a lot of time. I no longer have to look up the blockquote markup and I can focus on writing the content. When writing, anything that gets the tech out of the way is a good thing for me.

At some point, I'll style `<figurecaption>` to indent it to the same level as the blockquote. I think this will visually tie the author and citation to the body of the quote itself.
