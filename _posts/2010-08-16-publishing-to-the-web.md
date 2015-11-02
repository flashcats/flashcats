---
title: Publishing to the Web!
author: bear
layout: post
permalink: /2010/08/16/publishing-to-the-web/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Easy
---
Just a quick post on how to get everything uploaded to the web. Before you get started, you will need some form of [web hosting][1], to serve your content to people requesting it. If you're looking for hosting, you can check out some of the large companies like BlueHost, HostGator, or WebFaction to at least get an idea of plans and pricing.

When you've finished a project in Flash Catalyst, you can publish it via the File > Publish option. This creates two versions of your project.

<a href="http://flashcats.net/wp-content/uploads/2010/08/published.png" rel="lightbox[421]"><img class="aligncenter size-full wp-image-422" title="Publish Contents" src="http://flashcats.net/wp-content/uploads/2010/08/published.png" alt="" width="406" height="190" /></a>

More after the jump.

<!--more-->

We will be using the deploy-to-web version. If you're curious about what the differences are, check out this [previous post][2]. The contents of the deploy-to-web folder look like this.

<a href="http://flashcats.net/wp-content/uploads/2010/08/published-contents.png" rel="lightbox[421]"><img class="aligncenter size-full wp-image-423" title="Deploy To Web Contents" src="http://flashcats.net/wp-content/uploads/2010/08/published-contents.png" alt="" width="367" height="568" /></a>Here are the key players

  1. Main.swf - this is your project, published in swf form.
  2. Main.html - an html page that loads Main.swf
  3. assets - folder containing all the linked assets (movies, images, sound clips, swfs) for your project.
  4. swfobject.js - some JavaScript that helps Main.html load Main.swf
  5. Flex libraries - all the files ending in .swz are Flex libraries. All Catalyst functionality is built on top of the Flex framework. If these libraries are missing, Flash can load these libraries from a central Adobe server, but it might be slower.

You will need to find out how to upload content to your web host. If you search their documentation for "Uploading Content with FTP" you can probably find something to start with. If you upload the deploy-to-web folder, then your web page will be available at *yourwebaddress/deploy-to-web/Main.html*. Many people just upload the contents of the deploy-to-web folder rather than the folder itself, so that the address is *yourwebaddress/Main.html*. Unless you know exactly what each file is doing, I'd recommend making sure you upload the entire contents of the deploy-to-web folder.

If you don't specify a file (eg *Main.html*), then most web servers will default to one called *index.html* or *default.html*. So, if you rename Main.html to index.html, you will now be able to view your published project at *yourwebaddress*.

 [1]: http://en.wikipedia.org/wiki/Web_hosting_service
 [2]: http://flashcats.net/2010/06/23/run-local-vs-deploy-to-web/