---
title: "Twitter card and Open Graph images in the Icarus theme for Hugo"
layout: post
categories: ["Content design", "Hugo", "Social media"]
tags: ["Facebook Open Graph", "Hugo", "Icarus theme", "Metadata", "Social media", "Twitter", "Twitter card"]
---

When sharing a post from my music blog to Facebook, the post images did not appear in the link preview.

![Facebook update shows text, link and no image](/assets/2016/07/fb-link-preview-without-image.png)

The lack of images is due to a missing `og:image` property in my post metadata.

I found some information on how to populate this property in the [Icarus theme for Hugo](http://themes.gohugo.io/theme/hugo-icarus/) in a [post by Brendan Quinn](http://brendan-quinn.xyz/post/working-with-hugos-internal-partial-templates-facebook-and-open-graph/).

Brendan shared his code for Hugo's internal partial templates to populate values for the [Facebook Open Graph](https://developers.facebook.com/docs/sharing/opengraph).

Most of the code goes over my head but I noticed the following line in his example post frontmatter:

```toml
images = ["http://brendan-quinn.xyz/css/images/banners/responsive-images-landscape-seo.jpg"]
```

I added the following line to my frontmatter:

```toml
images: ["/media/2016/07/20160721-little-walter-820x350.jpg"]
```

The republished post now contains these two lines of metadata:

```html
<meta property="og:image" content="http://twang.city/media/2016/07/20160721-little-walter-820x350.jpg" />
<meta name="twitter:image:src" content="http://twang.city/media/2016/07/20160721-little-walter-820x350.jpg"/>
```

The link preview now includes the defined image, which you can check with Facebook's [Sharing Debugger](https://developers.facebook.com/tools/debug/sharing/):

![Link preview with image as seen in Facebook Sharing Debugger](/assets/2016/07/fb-link-preview-with-image.png)

Similarly, checking the same URL with Twitter's [card validator](https://cards-dev.twitter.com/validator) shows the image displayed in the card preview:

![Preview of Twitter card with image included](/assets/2016/07/tweet-card-validation.jpg)
