---
title: "Limit Hugo's RSS feed to recent content in a single directory"
layout: post
categories: ["Hugo"]
tags: ["Hugo", "RSS"]
---

Hugo's default [RSS template](https://gohugo.io/templates/rss/#the-embedded-rss-xml) publishes an unlimited number of items and shows a summary rather than full content. Also, the feed URL and the content Hugo generates vary depending on the active page's content type: post, page, section, category or tag.

For this site, I publish one RSS feed with the following attributes:

- full content so that readers do not have to leave their RSS client
- most recent 15 posts in the `/blog` directory
- my name as the feed title
- the descriptive URL `/feed.xml`

To create a similar feed for your Hugo site, follow these steps:

1. Create a new file in your theme directory at:

    ```xml
    /layouts/_default/rss.xml
    ```

2. Copy the Hugo [RSS template](https://gohugo.io/templates/rss/#the-embedded-rss-xml) and paste it in `rss.xml`.

3. In my site's `config` file, I declare my name in the `author` parameter. To use the same parameter as the feed title, in `rss.xml` change the feed's `<title>` tag to:

    ```go
    <channel>
    ...
      {% raw %}<title>{{ $.Site.Params.author }}</title>{% endraw %}
    ...
    </channel>
    ```

4. For consistency with the feed title, simplify the channel's `<description>`:

    ```xml
    <channel>
    ...
      <description>Recent blog posts by {% raw %}{{ $.Site.Params.author }}{% endraw %}</description>
    ...
    </channel>
    ```

5. By default, Hugo publishes all items in the feed:

    ```go
    {% raw %}{{ range .Data.Pages }}{% endraw %}
    ```

    To show the most recent 15 items and to constrain items to those in one directory, for example, `/blog`, change the `range` to:

    ```go
    {% raw %}{{ range first 15 (where .Data.Pages "Section" "blog") }}{% endraw %}
    ```

6. To show the item's full content in the feed, change the item's `<description>` to:

    ```xml
    <item>
    ...
      <description>{% raw %}{{ .Content | html }}{% endraw %}</description>
    ...
    </item>
    ```

7. Hugo renders the feed at `/index.xml` by default. You can specify your own URL in your `config` file. For example, `feed`:

    ```toml
    [outputs]
      home = [ "HTML", "RSS" ]

    [outputFormats]
    [outputFormats.RSS]
      mediatype = "application/rss"
      baseName = "feed"
    ```

Here's a preview of the feed in the [feedly RSS client](https://feedly.com):

![Recent items shown in feedly](/assets/2018/05/feedly-min.jpg)
