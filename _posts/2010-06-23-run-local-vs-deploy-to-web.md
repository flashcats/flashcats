---
title: run-local vs deploy-to-web
author: bear
layout: post
permalink: /2010/06/23/run-local-vs-deploy-to-web/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Easy
tags:
  - deploy to web
  - publish
  - run local
---
If you've published your project in Catalyst yet, you've probably noticed that Catalyst creates two different versions of your project in the publish folder. One is the run-local version, and the other is the deploy-to-web version. So what's the difference?

<!--more-->

Because of security restrictions, when your swf runs, it is allowed to load files from your computer's filesystem, or from the network, but not both. If your swf is on a web server, then it needs to load files (linked images, video, sound clips) with network url requests. These requests are along the lines of "grab me resource x at location http://www.server.com/path". If your swf is on your hard drive, then it needs to load files from the local file system. These requests would be along the lines of "grab me resource x at location file://local-file-path".

The framework Catalyst is built upon, Flex, also needs to load some resources at runtime. Like all those .swz files lying around in your publish directories. Which means that even if your project doesn't load linked images, movies, sound files, or swfs, it does load these libraries. Your deploy-to-web swf won't load correctly from your local filesystem, and your run-local swf won't load correctly from a server.

Here's how you should use these two different swfs.

  1. When running your Catalyst project from a local filesystem (hard disk, cd-rom, usb drive), use the run-local version.
  2. When putting your Catalyst project onto a web server, use the deploy-to-web version.