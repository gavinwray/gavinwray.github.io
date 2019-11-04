---
title: "Designing with grids"
layout: post
categories: ["Content design"]
tags: ["Design", "Grids", "Information architecture", "Layout", "Learning", "Sketching", "Web design"]
---

With my new portfolio design finished and live, it's time to catch up on writing posts. This post documents the design process I worked through in creating this website.

As I mentioned in my last [update on what I'm doing](/2010/04/27/an-update-on-what-im-doing/), I wanted to develop my design knowledge and put it into practice. I spent some time studying grid layouts and typography, getting stuck into two books in particular:

* [Grid Systems: Principles of Organizing Type](http://www.amazon.co.uk/gp/product/1568984650?&tag=gavwra-21) by Kimberly Elam
* [A Practical Guide to Designing for the Web](http://fivesimplesteps.com/books/practical-guide-designing-for-the-web) by [Mark Boulton](http://www.markboulton.co.uk/)

These two books forced me to consider the portfolio layout in detail. Elam's book is quite theoretical, which is a good thing when you're learning a new subject. Boulton's bookhelped me consider the grid theory in terms of the web.

![Red grid overlaid on a poster for the Institute for Architecture and Urban Studies](/assets/2010/06/elam-grid-overlay-540.jpg)

Page 43, Kimberley Elam's _Grid Systems_

Boulton's chapter on layout helped me to consider grid layouts that work aesthetically yet always keeping in mind that I'd eventually have to turn the grid design into code for a WordPress theme.

![Mark Boulton's grid layout for De Staandard website](/assets/2010/06/boulton-grid-layout-540.jpg)

Page 235 in Mark Boulton's _A Practical Guide to Designing for the Web_

To work through this process, I chose the [grid960.gs system](http://960.gs/). This contains sketch sheets, an HTML layout generator and CSS with consistent measurements to help streamline web development from design through to coding.

## Sketching

With a content plan for the portfolio already in place, my first step was to sketch the content type templates using [Nathan Smith's sketch sheets](http://github.com/nathansmith/960-Grid-System/tree/master/sketch_sheets/):

* home page
* about page
* portfolio index
* portfolio item
* blog index
* blog post
* contact

![Sketch of home page using a 12 column grid](/assets/2010/06/home-page-sketch-540.png)

Home page sketch ([view full size image on flickr](http://www.flickr.com/photos/gavinwray/4707084254/))

![4 sketches of portfolio item template](/assets/2010/06/project-detail-sketch-540.png)

Portfolio item sketches ([view full size image on flickr](http://www.flickr.com/photos/gavinwray/4707087866/))

## Wireframes

Next, I grabbed the 12-column [960 template psd](http://github.com/nathansmith/960-Grid-System/tree/master/templates/photoshop/), opened it in [Pixelmator](http://www.pixelmator.com/) and drew wireframes of each page template.

Back using Boulton's chapter on layout, I used his advice on the [rule of thirds](http://en.wikipedia.org/wiki/Rule_of_thirds):

> “Photographers have used the Rule of Thirds for years, who borrowed it from, yet again, classical artists and architects. The theory is simple – which is why it's easy to apply in your day-to-day design work. Divide any workspace, or layout, into thirds horizontally and vertically, and align key focus points of your composition to where the lines intersect.”

A web design at 960px wide breaks nicely into three columns of 320px each. With a 10px gutter either side of each column, you now have 300px wide blocks for the content, which, again, is a perfect number to further sub-divide by three (giving 100px blocks).

In this closeup of the home page's top left corner, I used the rule of thirds on the horizontal spacing. You can see the different elements (title, navigation bar, summary text in bold and the call to actions) aligned to the grid at units of 50 or 100 pixels.

![Home page wireframe with grid overlay showing alignment of key sections based on the rule of thirds](/assets/2010/06/home-wireframe-grid-overlay.png)

You can also see the content blocks on the portfolio page arranged in three columns, each block 300px wide and 300px high:

![Portfolio index wireframe with grid overlay - the content boxes are 300 pixels wide](/assets/2010/06/folio-grid-overlay.png)

## Summary

You may wonder why it's worth going through this detailed grid design process. Is it too detailed? Should you fire up your image editor and just dive in?

Everyone has different ways of working. This is a personal braindump of the thought processes I've worked through. I think using grids is a valuable exercise, particularly if you find the visual side of web design difficult.

By using grids to focus purely on layout, alignment and white space, you simplify the visual design process. Separating layout from colour and typography reduces the number of design elements and choices to make at once. You can see the effect of small changes more easily and adjust as you work.

Ever have those times when you stare at your design and think ‘this doesn't look right’ but you don't know why? Focusing on layout and white space makes it easier to deal with these problems. Something doesn't feel right? Check your units of measurement and re-align. Does it ‘feel’ better now?

An organised layout based on grids, using consistent measurements, can begin to feel like a good web design, even before you introduce colour and type.
