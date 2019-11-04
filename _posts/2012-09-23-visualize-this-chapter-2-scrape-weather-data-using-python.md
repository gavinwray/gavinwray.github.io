---
title: "'Visualize This' chapter 2: scrape weather data using Python"
layout: post
categories: ["Content management"]
tags: ["Books", "Data", "Learning", "Programming", "Python", "Scraping", "Visualisation", "Weather"]
---

This weekend I started working through the _[Visualize This: The FlowingData Guide to Design, Visualization and Statistics](http://book.flowingdata.com/)_ by Nathan Yau, the writer and data visualisation expert behind [flowingdata.com](http://flowingdata.com/).

I've been interested in this field for some time but haven't invested the time to learn the new technical skills, partly through fear of programming. So, I sat down with the book, opened a text editor on my Mac and fired up Terminal.

The first practical exercise in Yau's book uses [Python](http://en.wikipedia.org/wiki/Python_(programming_language)) and the [Beautiful Soup](http://www.crummy.com/software/BeautifulSoup/) Python library to scrape historical temperature data from [Weather Underground](http://www.wunderground.com/) (chapter 2, pages 30–37). The principle is to automatically scrape the maximum temperature in one location for every day in 2009, rather than load a separate web page for each day manually and record the maximum temperature yourself. Doing that 365 times would be tedious.

However, it probably would have been faster than the two or three hours I spent trying to get this first introductory exercise to work on my Mac!

As someone new to Python, installing things via Terminal and basic Terminal commands, this exercise was difficult. Rather than doing the actual task, I had to learn things around it first. That's ok.  That's what learning is.

I found this first exercise difficult though so, in the hope of saving other people confusion, here are my notes in context with quotes from Yau's instructions, filling out some of the detail that may help others get through it.

## Install Python

Page 30:

> "If you work on Mac OS X, you should have Python installed already. Open the Terminal application and type **python** to start."

If you've never done any programming before, and I suspect plenty of the book's readers haven't, you might be thinking ‘what is the Terminal application?’

1. Open a Finder window.
2. Go to **Applications > Utilities**. The Terminal application is in here.
3. Double-click on Terminal to open it. The Terminal application looks like a text editor.
4. In the new Terminal window, type `python`. You should now see something like this:

![Screenshot of Terminal: install Python](/assets/2012/09/terminal-install-python.png)

## Download Beautiful Soup

Page 30:

> "Next, you need to download [Beautiful Soup](http://www.crummy.com/software/BeautifulSoup/), which can help you read web pages quickly and easily. Save the Beautiful Soup Python (.py) file in the directory that you plan to save your code in. If you know your way around Python, you can also put Beautiful Soup in your library path, but it'll work the same either way."

I went to the [Beautiful Soup website](http://www.crummy.com/software/BeautifulSoup/#Download) and downloaded Beautiful Soup 4.1.3, the current version at the time of writing. It's a folder, not a file, but I kept going and saved this folder to where I was planning to do the scraping weather data:

![Beautiful Soup 4.1.3 directory contents in Finder](/assets/2012/09/beautiful-soup-4.1.3-directory.png)

So far, so good.

## Full script for get-weather-data.py

This is where I got stuck. Beautiful Soup has changed since the book was published in 2011. The first two lines of code in Yau's `get-weather-data.py` file are:

```py
import urllib2
from BeautifulSoup import BeautifulSoup
```

This does not work with Beautiful Soup version 4 onwards. Thankfully, I found [Dikei's solution on Stackoverflow](http://stackoverflow.com/a/9877397/722673). Change the second line in `get-weather-data.py` to:

```py
from bs4 import BeautifulSoup
```

## Run the code

Page 37:

> "The only thing left to do now is to run the code, which you do in your terminal using: `$ python get-weather-data.py`"

Taking this literally, back in your Terminal window, you get an error message:

![Run Python script error](/assets/2012/09/terminal-run-python-script-error.png)

There's a crucial step missing from Yau's instructions. In Terminal you need to navigate to the directory where you saved Beautiful Soup.

Firstly, if you still have the same Terminal window open from when you installed Python, you get stuck again. This is what I did:

1. In the Terminal menu, go to **Shell > New Window**.
2. In the Terminal window, type `cd` followed by the path to the directory where you have saved your `get-weather-data.py` file. For example:

``` txt
cd /Users/gavinwray/Documents/Books/Visualize-This-by-Nathan-Yau/Gavin/ch02/weather-scrape/beautifulsoup4-4.1.3
```

Now that's a long path name and easy to make a typo with. Two things I learnt here that might save you frustration:

* The `get-weather-data.py` script only runs if the path to the directory where it is saved does not contain spaces. For example, if you've got a directory called `/Visualize This/chapter 02/` in your file path, the script does not run.
* To save typing the full path, you can copy it by right-clicking on the directory name in Finder and choosing **Copy**. This copies the file path and you can paste it directly into your Terminal window. (Thanks [Max Woolf](http://max.woolf.io/) for showing me this shortcut.)

So, you should now see your Terminal window showing something like this:

![Changed directory](/assets/2012/09/terminal-cd.png)

## Be patient

Page 37:

>"It takes a little while to run, so be patient. In the process of running, your computer is essentially loading 365 pages, one for each day of 2009. You should have a file called `wunder-data.txt` in your working directory when the script is done running."

`wunder-data.txt` was written to my directory immediately and the Terminal window appeared to hang, like this:

![Get weather data](/assets/2012/09/terminal-run-script.png)

Now you do have to be patient. The script took about 15 minutes to complete on my machine.

15 minutes later, huzzah, I have a comma-delimited file with 365 rows, one for each day in 2009 (now in [Google Spreadsheets](https://docs.google.com/spreadsheet/ccc?key=0AmowvGiVeqSBdFhMZHRKOTNWVTh1c0RIU0pEQnVpbEE)) showing the maximum temperature reached that day in Birmingham.

Before yesterday, I would never have thought I could be overjoyed at such a result. Maybe my geek kudos has just gone up a few points while see-sawing another personality rating rapidly down. Hopefully, though, what I learnt yesterday will save people trying out this exercise the confusion I did.
