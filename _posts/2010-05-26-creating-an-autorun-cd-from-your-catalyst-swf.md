---
title: Creating an Autorun CD from your Catalyst Swf
author: bear
layout: post
permalink: /2010/05/26/creating-an-autorun-cd-from-your-catalyst-swf/
aktt_notify_twitter:
  - no
categories:
  - Moderate
tags:
  - autorun
  - cd
  - flash drive
  - projector
---
If you've created a presentation or demo in Catalyst that you'd like to start up automatically from a CD or flash drive, then this tutorial is for you.

<!--more-->What you'll need:

  1. A Flash Catalyst project you'd like to autorun

Here's what you do:

  1. Publish your Flash Catalyst project, and open the run-local folder
  2. Open Main.swf with Adobe Flash Player (Right Click -> Open With -> Adobe Flash Player)
  3. Under Flash Player's File menu, choose Create Projector. A projector is a native application wrapper for your swf, a .app on Mac or a .exe on Windows. This is what you'll autorun.
  4. Create a file named AutoRun.inf with a program like Notepad, and add the lines  
    [AutoRun]  
    open=projector.exe
  5. Replace projector.exe with the filename of your projector from Step 3.
  6. Burn AutoRun.inf, your projector from Step 3, and the assets folder from run-local version of your published project to your CD, or place them on removable media like a flash drive.

You're done! As you may have noticed, the autorun feature will only work with PCs. You can read more about autorun in this [article][1]. You can still create a Mac projector and place it on your CD, but Mac OS X doesn't have the same autorun feature as PCs.

 [1]: http://kb2.adobe.com/cps/133/tn_13374.html