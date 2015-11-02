---
title: Using a Custom Preloader in Catalyst
author: bear
layout: post
permalink: /2011/04/11/using-a-custom-preloader-in-catalyst/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Builder Tweaks
---
A common request for Catalyst is the ability to customize the preloader that displays while the main swf is loading. I've tweaked some FXP's and FXPL's to simplify the process of modifying the preloader in Catalyst.

For an example, click the image below.

[<img class="aligncenter size-full wp-image-580" title="preloader" src="http://flashcats.net/wp-content/uploads/2011/04/preloader.png" alt="" width="318" height="100" />][1]

FXP(L)s and instructions after the jump.

### <!--more-->To start a new project with a custom png preloader

  1. Download the [Preloader-Png FXP][2]
  2. Open the FXP in Catalyst
  3. Import the png you would like to use, and rename it "preloader.png"

### To start a new project with a custom swf preloader

  1. Download the [Preloader-Swf FXP][3]
  2. Open the FXP in Catalyst
  3. Import the swf you would like to use, and rename it "preloader.swf"

This swf must be a simple AS3 movie clip (you can't use a swf created in Catalyst).

### For an existing project

Here's the longer way to customize the preloader on an existing project (you can use a png, gif, jpg, or swf)

  1. Download the [Preloader FXPL][4]
  2. Open your project in Catalyst
  3. Import the FXPL
  4. Import the png, gif, jpg or swf you are going to use as the preloader
  5. Save your project as an FXP, and import it into Builder
  6. Open Main.mxml (the application file under src > default package)
  7. At the end of the <Application> tag, add the attribute preloader="preloader.CustomPreloader"
  8. In PreloaderUrl.as (under the src > preloader package), replace "preloader.png" with the name of your preloader asset
  9. That's it, you can export your project as an FXP and open it up again in Catalyst

For some preloader inspiration, check out [PrettyLoaded][5]  
The source for the preloader is a modified version of the code [here][6].  
If you want a progress-bar like preloader, check out [this video][7] over at gotoAndLearn or Jesse Warden's [tutorial][8].

Happy preloading!

 [1]: /static/custom-preloader/Main.swf
 [2]: http://dl.dropbox.com/u/21428091/Preloader-Png.fxp "Png Preloader"
 [3]: http://dl.dropbox.com/u/21428091/Preloader-Swf.fxp "Swf Preloader"
 [4]: http://dl.dropbox.com/u/21428091/Preloader.fxpl "Preloader"
 [5]: http://www.prettyloaded.com
 [6]: http://npacemo.com/wordpress/2008/07/06/flex-application-bootstrapping-totally-custom-preloader/
 [7]: http://www.gotoandlearn.com/play.php?id=108
 [8]: http://jessewarden.com/2007/07/making-a-cooler-preloader-in-flex-part-1-of-3.html