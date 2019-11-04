---
title: "Updated blockquote post snippet for WordPress"
layout: post
categories: ["WordPress"]
tags: ["Blockquote", "HTML", "PHP", "WordPress"]
---

Earlier this year I wrote a [post](/2013/02/01/reusable-blockquote-markup-in-wordpress-using-post-snippets/) on using [A List Apart's official blockquote pattern](https://gist.github.com/murtaugh/4489740) as a reusable snippet with the [Post Snippets](http://wordpress.org/plugins/post-snippets/) plugin for WordPress.

The original snippet code relied on values for four variables:

```php
{quote}
{author}
{source}
{sourceurl}
```

They combine to produce a blockquote that renders like this:

> One of the most important aspects of a good IA is that it works well for the people who need to use it.

Donna Spencer, [A Practical Guide to Information Architecture](http://practical-ia.com/)

## Updated snippet

[Anders Gressli](http://anders.gressli.net/) kindly improved the snippet to omit unnecessary markup when a value for any variable is empty. For example, an empty anchor is omitted when you don't specify a value for `{sourceurl}`.

```php
[php]
echo '<figure class="quote">';
echo '<blockquote>"{quote}"</blockquote></figure>'; 
// the double quotation marks surrounding the quote text are aesthetic
if( "{author}"){
  echo "<figcaption>{author}";
    if( "{sourcetitle}" != ""){
      if( "{sourceurl}" != ""){
        $url_start = '<a href="'.">';
        $url_end = '</a>';
      }
      echo ", <cite>".$url_start."{sourcetitle}".$url_end."</cite>";
    }
    echo "</figcaption>";
  }
echo '</figure>';
[/php]
```

## Using the snippet in WordPress

To use this markup with the Post Snippets plugin:

1. In your WordPress dashboard, go to **Settings > Post Snippets**.

2. Select **Add New Snippet**.

3. Give the new snippet a title, such as **Blockquote**.

4. Enter the following in the **Variables** field:

    ```txt
    quote,author,sourcetitle,sourceurl
    ```

5. Select **Shortcode** and **PHP code**.

6. Copy the snippet code above and paste it in the snippet box.

7. Select **Update Snippets** to save your changes. Your settings in the WordPress dashboard should look like this:

    ![Post snippet settings](/assets/2013/12/add-new-snippet-settings1.png)

8. To use the snippet when writing a post, in the toolbar, select **Insert a Post Snippet**.

9. Enter your values in the pop-up window:

    ![Insert a blockquote pop-up](/assets/2013/12/add-blockquote-pop-up.png)

## Test 1 - all variables

Let's try it out.

This quote contains values for all four variables:

```html
[Blockquote v2 quote="One of the most important aspects of a good IA is that it works well for the people who need to use it." author="Donna Spencer" sourcetitle="A Practical Guide to Information Architecture" sourceurl="http://practical-ia.com/"]
```

It generates this markup:

```html
<figure class="quote">
  <blockquote>One of the most important aspects of a good IA is that it works well for the people who need to use it.</blockquote>
  <figcaption>Donna Spencer, <cite><a href="http://practical-ia.com/">A Practical Guide to Information Architecture</a> </cite></figcaption>
</figure>
```

## Test 2 - no source URL

The snippet:

```html
[Blockquote v2 quote="One of the most important aspects of a good IA is that it works well for the people who need to use it." author="Donna Spencer" sourcetitle="A Practical Guide to Information Architecture" sourceurl=""]
```

The markup:

```html
<figure class="quote">
  <blockquote>One of the most important aspects of a good IA is that it works well for the people who need to use it.</blockquote
  <figcaption>Donna Spencer, <cite>A Practical Guide to Information Architecture</cite></figcaption>
</figure>
```
