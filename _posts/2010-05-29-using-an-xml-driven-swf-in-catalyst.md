---
title: Using an XML-Driven Swf In Catalyst
author: bear
layout: post
permalink: /2010/05/29/using-an-xml-driven-swf-in-catalyst/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Advanced
  - Library Assets
tags:
  - external files
  - slideshow
  - swf
  - xml
---
There are some really cool Flash resources out there that are driven by external files. For example, I used the demo version of [SlideShowPro][1] to create a Flash slideshow. The resulting swf relies on some xml and image files to properly render. I wanted to bring this into a Catalyst project, the result of which you can see below.

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/xmlslideshow/Main.swf" width="400" height="300" targetclass="flashmovie" allowfullscreen="true" base="/static/xmlslideshow/"]

[![Get Adobe Flash player][2]][3]

[/kml_flashembed]

The awesomeness you see above is all SlideShowPro. This post is just about bringing the SlideShowPro swf into a Catalyst project.

More after the jump.

<!--more-->If you're curious about how I created the slideshow, check out the SlideShowPro 

[website][4]. All I'm going to say is that I used the Flash component, because working with the standalone swf requires some additional tweaking outside of Catalyst.

The resulting slideshow had the following resource structure.

<img class="aligncenter size-full wp-image-115" title="Swf Folder Structure" src="http://flashcats.net/wp-content/uploads/2010/05/slideshowpro-folderstructure.png" alt="The folder structure for the slideshowpro swf" width="171" height="189" />The swf I want to include in Catalyst is slideshowpro.swf. Slideshowpro.swf uses the param.xml and images.xml files to configure itself, and the image files in the gallery folder properly render. I'm going to explain how to get slideshowpro.swf working in Catalyst, and then there's a slightly longer explanation section at the end.

### Getting it Working in Catalyst

To get the slideshow working in Catalyst:

  1. Look at all the resources in the same folder as your swf, and note the ones that your swf needs. In this case, slideshowpro.swf requires: params.xml, images.xml, and the gallery folder.
  2. Import the swf into Catalyst. You can work with it just like any other swf; move it, resize it, place it in various components, states, whatever.
  3. Run / Preview your project (Ctl/Cmd-Enter). You'll notice that the swf won't render properly. This is because Catalyst only imported the swf, and not the other files that the swf needs.
  4. Note the address of the previewed project in your browser. It's the location of the Main.html file Catalyst is previewing for you. You want the "Project" folder, which contains "bin-debug" which contains the Main.html file.  
    On Mac, it's  
    /Users/*username*/Library/Application Support/Adobe/Flash Catalyst/workspace/Project/bin-debug
  5. Open this folder in your operating system. Open the "src" folder.
  6. Copy all of the required resources (from step 1) there.
  7. Save your project. Try running it again. You may have to close the project and reopen it to see the swf properly loading the desired files.

Congratulations, you're done!

### The Explanation Bit

I'm going to do a bit of explanation, in case you're wondering why it works this way.

The source folder is where all of your project resources live. Placing files or folders there means they will be copied to the same location as the Main.swf Catalyst generates, either in the preview folder (bin-debug), or the publish run-local and deploy-to-web folders.

SlideShowPro and many other swfs request external resources with relative ("params.xml"), rather than absolute paths ("C:\Documents and Settings\username\...\params.xml"). By default, the Flash player looks for these file paths relative to the base path of the swf's top level container. This behavior is less complex than it sounds. Here are a couple cases using slideshow.swf, which requests a file with relative path "params.xml".

  1. You open slideshow.swf. Slideshow.swf is the top level container. The Flash Player looks for params.xml in the same folder as slideshow.swf.
  2. You open Main.swf, which contains slideshow.swf. Main.swf is the top level container. The Flash Player looks for params.xml in the same folder as Main.swf.
  3. You open Main.html, which contains Main.swf which contains slideshow.swf. Main.html is the top level container. The Flash Player looks for params.xml in the same folder as Main.html.

You could place Catalyst's Main.swf in many different html pages. With the default behavior for a swf's base path, you would have to copy your external resources to all of the different folders containing those html pages. I wanted to keep everything relative to Main.swf, and fortunately there's a way to do just that. When you embed a swf, you can set the location of the swf's base path using the *base* parameter. This tells the Flash Player where to look for relative file paths. Embedding swfs in a web page is beyond the scope of this tutorial, but there is a great resource covering the topic over at [Adobe][5]. As a sidenote, you'll want to enable fullscreen, so slideshowpro can do it's awesome fullscreen behavior.

 [1]: http://slideshowpro.net/products/slideshowpro/
 [2]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [3]: http://adobe.com/go/getflashplayer
 [4]: http://slideshowpro.net/
 [5]: http://kb2.adobe.com/cps/127/tn_12701.html