---

layout: update
published: true

collection: updates
category: chrome
product: chrome
type: news
date: 2014-03-20

title: "Get on the CSS Grid!"
description: "CSS Grid Layout is a new CSS3 module that provides new layout primitives that are ideal for web applications."
article:
  written_on: 2014-03-20
  updated_on: 2014-03-20
authors:
  - alexdanilo
tags:
  - layout
  - css
  - grids
permalink: /updates/2014/03/Get-on-the-CSS-Grid.html
---
When building a Web Application, one of the first things that's needed is a way to lay out the content of your app.

Lots of designers use imaginary grids to lay out content, whether it's for a site or app. The CSS group has been working hard to make layouts easier, and as part of that have produced the [CSS Grid Layout Module](http://www.w3.org/TR/css-grid-1/) which is now emerging in browsers.

This feature is available to try out in Chrome behind an experimental flag. It's also implemented in IE since version 10, and likely to be in most browsers soon.

### Executive summary

* CSS Grid Layout lets you define rows and columns for your layout
* Grids can adapt to make use of available space
* Content order can be independent from grid container display order
* Layouts can change based on media queries, making responsive design easier
* Content can overlap (enabling layout that's impossible with other methods)
* Grid Layout is fast

Here's an overview video that explains a lot about how CSS Grid Layout works ([slides are here](http://sydcss-grid.appspot.com/""):

{% video //www.youtube.com/embed/hy7IMGVUHps %} {% endvideo %}

### Try it out

Using CSS Grid Layout in Chrome now is easy. First thing you need to do is turn on the experimental flag to enable the feature.

First load the _chrome://flags_ URL and scroll down to the option to _Enable experimental Web Platform features_ as shown below:

<img src="http://sydcss-grid.appspot.com/images/enable-flag.png" alt="Image of experimental flag option"/>

Just click _Enable_ to turn the flag on, and you should see a prompt to restart the browser that looks like this:

<img src="http://sydcss-grid.appspot.com/images/enable-relaunch.png" alt="Image of Relaunch button"/>

Now just click the _Relaunch Now_ button to restart your browser and you'll be all set to try out CSS Grid Layout.

### Let us know what you think

CSS Grid Layout is a great new primitive for web content, but as usual we're all keen to hear what developers think about it. There are lots of ways to give feedback - leave a comment here, send mail to the [W3C CSS Working Group list](mailto:www-style@w3.org) with "[css-grid]" in the subject line, log bugs, or blog and tweet what you think of it. We look forward to seeing the great layouts you build with this super useful new feature.
