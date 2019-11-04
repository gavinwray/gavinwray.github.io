---
title: "Refactoring a Hugo theme's stylesheet"
layout: post
categories: ["Hugo", "Process"]
tags: ["CSS", "Hugo", "Responsive design", "Web design"]
---

I moved this blog from [WordPress to Hugo](/2017/12/goodbye-wordpress-hello-hugo/) in December 2017 to learn about static site generators and to practise maintaining a site using modern processes like Git. I chose the [Future Imperfect theme](https://github.com/jpescador/hugo-future-imperfect) as a foundation and put my own styles in `add-on.css`, which takes precedence over the theme's stylesheet `main.css`.

Override stylesheets are useful. You can restyle elements of a theme yet leave the core styles such as layout and typography intact. When a new version of the core stylesheet is available, you can upgrade a theme without affecting your override stylesheet.

Over time though, override stylesheets can bloat. Four months after switching to Hugo, I reached a tipping point. Battling [precedence](https://css-tricks.com/precedence-css-order-css-matters/) conflicts and unwanted cascades between `add-on.css` and `main.css` took too much time. I wanted a tidy, maintainable theme and to commit more time to blogging.

## Confidence

[Refactoring](https://en.wikipedia.org/wiki/Code_refactoring) a theme can be a scary, significant undertaking. `main.css` has 2,500 lines while my `add-on.css` has reached 1,000 lines.

As well as merging these stylesheets into one file, I wanted to edit other parts of the theme, which is written in the [Go](https://golang.org/) language. I'm no programmer. I scrape through by reading manuals or trial and error.

Two things gave me the confidence to jump in:

* A day of [front-end web development training](https://matmannion.com/a-first-foray-into-training/) (and the prep work) by Mat Mannion. He encouraged me to think more like a developer and "to get more into a mindset of building a house than painting a wall"
* Adam Silver's book _[MaintainableCSS](https://maintainablecss.com/)_, which has principles and practical examples of how to write modular and maintainable CSS

## Approach

Before writing a line of CSS, I decided on three principles:

1. Design for small screens first and progressively add style for wider breakpoints. This meant inverting `main.css`’s large-screen-first-then-down structure of media queries.
2. Write in [LESS](http://lesscss.org/) instead of CSS to take advantage of [variables](http://lesscss.org/features/#variables-feature) and to be more efficient.
3. Define a new typography scheme with a larger base font size, and vertical rhythm and spacing based on ems.

## Responsive breakpoints

I prefer names related to scales rather than devices such as `-tablet` or `-mobile`. At the top of `main.less`, I defined breakpoint variable names inspired by T-shirt sizes:

```less
@screen-xxl-min: 1680px;
@screen-xl-max: 1679px;
@screen-xl-min: 1280px;
@screen-l-max: 1279px;
@screen-l-min: 980px;
@screen-m-max: 979px;
@screen-m-min: 736px;
@screen-s-max: 735px;
@screen-s-min: 480px;
```

## Colour palette

At the top of `main.less`, I defined colour variables with names prefixed with `gw-`. This helps me search for instances of the colour classes I use throughout the stylesheet. It also makes changing the whole site palette a swift task.

```less
@gw-green-mid: #2ab7ca;
@gw-green-dark: #1b7581;
@gw-green-light: #def2f4;
@gw-grey-dark: #3b4045;
@gw-grey-mid: #d2d2d5;
@gw-grey-light: #edeeef;
@gw-white: #fcfcfc;
```

Stating the colour in the class name conflicts with the HTML5 spec, which Adam Silver quotes in his [chapter on semantics](https://maintainablecss.com/chapters/semantics#10-because-the-standards-recommend-it):

> “&hellip; authors are encouraged to use values that describe the nature of the content, rather than values that describe the desired presentation of the content.”

I could use `@gw-colour-mid`, for example. In this instance though, as it's only me maintaining the stylesheet, I chose a variable name that's semantic to me.

## Typography

I reset the base font size to 16px for small devices and 20px for larger screens. The type scale is [1.200 Minor Third](http://type-scale.com/?size=20&scale=1.200&text=A%20Visual%20Type%20Scale&webfont=Nunito%20Sans&font-family=Nunito%20Sans%2C%20serif&font-weight=400&font-family-headers=&font-weight-headers=inherit&background-color=white&font-color=%23333):

![Font sizes for body text and headings](/assets/2018/06/visual-type-scale.png)

I optimised the post content's line length to maintain readability, and left- and right-hand white space, across all screen widths. The stylesheet has a lot of media queries to ensure a line length between 45 and 90 characters. The weighty, repetitive code is worth it though. For a succinct explanation, see Matthew Butterick's [Practical Typography](https://practicaltypography.com/line-length.html).

## Mini map

To help write the new stylesheet and tick off sections of `main.css` and `add-on.css` as I merged them, I used a mini map with `TODO:` comments at the top of `main.less`. The map outlines the stylesheet structure:

```css
/*
- Palette variables
- Breakpoint variables
- Reset
- Type
- Wrapper
- Header
    - Menu
    - Search
- Main layout
- Category list
- Portfolio list
- Post
- Sidebar
- Social share buttons
- Footer
*/
```

The structure of the stylesheet matches how I look at a site design, interpret the main elements and decide what order to do the work:

* colour palette
* responsive breakpoints
* typography
* main layout
* content
* footer

It's easy to go down a rabbit hole when styling the content so I try to focus on styling elements from left to right, top to bottom:

![Eye tracking across a page layout](/assets/2018/06/work-left-right.jpg)

When I get stuck or take a break, I leave `TODO:` comments in `main.less`. Wayou Liu's [TODO Highlight extension](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight) for Visual Studio Code helps me see these:

![Highlighted comment in Visual Studio Code](/assets/2018/06/to-do-highlight.png)

Searching the theme for `TODO` helps me find any parts I may have forgotten about.

## Compiling LESS to CSS

I'm using [Koala](http://koala-app.com/) to watch for changes to `main.less` and compile it to the theme's `main.css`. Using an app outside of the [Hugo build](https://gohugo.io/getting-started/usage/#the-hugo-command) and deploy process is not best practice though. I should work out how to include preprocessing and compiling as part of the Hugo site build. That's some chunky learning for another day.

For now, I have one maintainable stylesheet for the theme, a responsive mobile-first implementation and a clean visual aesthetic based on solid typography. The original 3,500 lines of CSS are a more manageable 2,000 lines of LESS.

Time for a brew.
