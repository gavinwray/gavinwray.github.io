---
title: "Custom stylesheet for the George Orwell essay archive"
layout: post
categories: ["Content design"]
tags: [
  "Accessibility",
  "CSS",
  "George Orwell",
  "GitHub",
  "Readability",
  "Typography",
  "Userstyles.org"
]
---

I found an archive of [George Orwell's essays in English and Russian language](http://www.orwell.ru/library/essays) while searching for a full-text version of _[Politics and the English Language](http://www.orwell.ru/library/essays/politics/english/e_polit)_ (1946). This essay contains Orwell's famous six rules for clear writing, which are touchstones for content people.

The site's typography makes for a difficult reading experience:

- long line lengths spanning the full width of the browser
- justified paragraphs rather than left-aligned (ragged right)
- tight leading

When reading long-form articles online, I prefer large sans-serif body text, constrained line lengths and leading between 1.3 and 1.5 [ems](https://en.wikipedia.org/wiki/Em_(typography)).

To improve the reading experience, I made a custom stylesheet with new typography for use with the Stylish browser extension. I've shared the stylesheet via [userstyles.org](https://userstyles.org/styles/141074/modern-typography-for-george-orwell-s-essays) and [GitHub](https://github.com/gavinwray/stylish-orwell).

## Before

![Politics and the English Language - before custom styles](/assets/2017/04/orwell-before-min.png)

Image: [orwell.ru](http://www.orwell.ru/library/essays/politics/english/e_polit)

## After

![Politics and the English Language - after custom styles](/assets/2017/04/orwell-after-min.png)

## Install via userstyles.org directory

1. Add the Stylish extension to your browser. The extension is available for [Chrome](https://chrome.google.com/webstore/detail/stylish-custom-themes-for/fjnbnpbmkenffdnngjfgmeleoegfcffe?hl=en), [Firefox](https://addons.mozilla.org/en-GB/firefox/addon/stylish/), [Safari](https://safari-extensions.apple.com/details/?id=com.sobolev.stylish-5555L95H45) and [Opera](https://addons.opera.com/en-gb/extensions/details/stylish/).

2. Visit [https://userstyles.org/styles/141074/](https://userstyles.org/styles/141074/).

3. Click **Install with Stylish**.

4. View any of the [essays](http://www.orwell.ru/library/essays/).

5. The Stylish extension should prompt you that styles are available for the current site. Accept the prompt and add the styles.

## Install manually

In Chrome the Stylish extension may not reliably prompt you that styles are available for the current site. 

To add the stylesheet manually:

1. Select the browser extension icon and select **Create new style**.

2. Give the style a name.

3. In [stylish.css](https://github.com/gavinwray/stylish-orwell/blob/master/stylish.css) copy all of the styles that are inside the `@-moz-document` and `url-prefix` rules.

4. Paste the styles in the **Code 1** box.

5. In the **Applies to** settings, choose **URLs starting with** from the drop-down list.

6. Enter `http://www.orwell.ru/library/essays/` in the box.

7. Select **Save**.
