---
layout: post
title:  "Improving BFF"
thumbnail: icon_improving_bff.png
date:   2016-12-08 08:11:00 -0500
categories: articles
tags: ux collaboration prototyping
---

<img src="/images/rocket.svg" class="hero">

<p class="p">One of the tools that came out of my efforts to prototype in code was <a class="link" href="http://bff.how/">BFF</a>.</p>

<p class="p">BFF stands for Barebones Functional Framework. It is a prototyping framework that I built by combining several open source
    tools like  <a class="link" href="http://gruntjs.com/">grunt</a>, some node modules, 3rd party front-end libraries (
     <a class="link" href="http://getbootstrap.com/">Bootstrap</a>,  <a class="link" href="http://fontawesome.io/">Font Awesome</a>, jQuery) all tied
    together by a custom barebones JavaScript framework (hence the name). I built it for people like
    my UX colleagues and I who are not seasoned front end developers. It was designed with speed in mind, and the
    ability to prototype in code far more rapidly, and far more easily than had been possible for me in the past.</p>

<p class="p">In BFF, there is a server side component and a client side component to the framework. On
    the server side, I am using grunt to fire up a web server, watch for changes, compile Sass files into CSS, and append
    a debugging URL to the end of the files to help debug JavaScript files in Chrome. On the client side, there is
    jQuery, Bootstrap, Font Awesome, and my custom JavaScript framework to help me quickly visualize what I'm designing.</p>

<p class="p">For the most part, I've developed BFF on my own and it shows. For the first year of its life,
    BFF was a little buggy, and not that fast on the Mac. This changed thanks to the generous contribution of a
    wonderful colleague of mine, Dori. Dori
    refactored the JavaScript engine, in the process fixing a lot of the performance issues and improving the quality of the
    code. Many times, I've started on InVision or a traditional design tool, gave up in frustration, and switched to BFF instead,
    because it was so much faster and easier to experiment with interactions. BFF is the reason why I continue to be bullish
    about prototyping in code.</p>

<p class="p">Over the last several months, I've started to run into technical issues with BFF.
    The BFF engine uses jQuery extensively to make the AJAX calls, and scan the HTML for <code>bff-</code> classes to parse and interpret. I love jQuery but
    it doesn't always work well with some frameworks like Angular. In addition, at my new job, I've been struggling to
    create a coded prototype, as the code I'm using as a starting point is dependent on jQuery 1.9.x while BFF uses
    jQuery 2 or higher.</p>

<p class="p">I've also had problems with using BFF with Amazon's AWS S3. BFF uses AJAX to load shared components. My
    coded prototypes work great locally and on traditional static web hosting but on S3, all I get is a blank
    screen.</p>

<p class="p">The dependency on third party libraries has been BFF's Achilles heel. The grunt plugins I use to launch the
    web server, watch for changes, and compile my Sass files
    have dependencies on an absolutely ridiculous amount of 3rd party libraries. And those libraries are dependent on
    other 3rd party libraries. The last time I checked my <code>node_modules folder</code>, there were over <strong>20,000</strong> files in nearly
    <strong>2,500</strong> folders with a total file size of <strong>200MB</strong>! One of the challenges with using node packages is that when I install
    and save them with <code>npm install [package] --save-dev</code>, npm assumes I want to use that specific version of the package only,
    and saves that information to package.json, instead of assuming I want the latest version. As 3rd party
    dependencies go out of date, the packages that depend on them start to output errors and finally break.</p>

<p class="p">This has been a major frustration with getting more widespread adoption of BFF. My goal with BFF was to
    make it easy enough for a UX designer with little experience with coding to pick up BFF and quickly start prototyping in
    code. Reality hasn't been as rosy. I've tried to install some of the projects that I originally developed with
    BFF and I can no longer run them locally with grunt and npm install.</p>

<p class="p">The good news is, the grunt and npm libraries are only there to speed development. The prototype themselves are
    completely static HTML, CSS, and JavaScript.
    I can launch my prototypes from any web server, from a local IIS install to a static web hosting service on the web, so as long as
    I have a web server (with the exception of Amazon S3) I can continue to view my prototypes. However, updating the
    prototypes becomes a little harder and a lot slower without my node packages to watch for changes and rapidly live
    reload the prototype on the fly.</p>

<p class="p">I'm starting to wonder if it's worth it to try and maintain BFF any longer. I'm not an experienced front
    end developer. It's not even my primary focus as a UX practitioner. While I do like prototyping in HTML, CSS, and I
    don't mind simulating interactions using some moderately complex JavaScript, maintaining a JavaScript framework, and
    debugging node and grunt errors is much harder.</p>

<p class="p">I still believe that prototyping in code is the way of the future when it comes to web and app design. I
    love it because it keeps my designs grounded in the real world. I can simulate designs for edge cases and with
    realistic data, and It makes it easier to test for various states like no data or large quantities of data,
    something that I've noticed a lot of designers tend not to factor into their designs.</p>

<p class="p">But, without the resources and experience to refactor BFF so I can fix these bugs and reduce the dependency
    on 3rd party plugins and libraries, it's going to get harder to continue prototyping in code. And that feels like a
    step backwards for my design workflow.</p>

<p class="p">I'm going to look around and see if there are any other designer friendly tools for prototyping in code.
    Or, I might just have to knuckle down and just make updating BFF a priority for the next couple of months. </p>