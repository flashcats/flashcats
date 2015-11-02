---
title: Creating An Image Gallery Using a Data List
author: bear
layout: post
permalink: /2010/07/26/creating-an-image-gallery-using-a-data-list/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Interactions
  - Moderate
  - Wireframe Components
---
Ever wanted to create an image gallery with more than 20 images? Ever wanted to play some more with Data Lists in Catalyst? Well, here's your chance. We're going to create an image gallery using Data Lists and the Design Time Data Panel, so that you can create an image gallery with as many images as you want. The end result of this tutorial will look something like the below image.

<a href="http://flashcats.net/wp-content/uploads/2010/07/slideshow-screenshot.png" rel="lightbox[341]"><img class="aligncenter size-full wp-image-342" title="Slideshow Screenshot" src="http://flashcats.net/wp-content/uploads/2010/07/slideshow-screenshot.png" alt="" width="220" height="222" /></a>

More after the jump.

<!--more-->

To start off, you'll need a bunch of images of roughly the same dimensions, and with roughly the same size as you'd like them to appear in your gallery. Import these into your project (File > Import).

Drag the first image onto the ArtBoard, and resize it to be the size of a single image in your gallery. Now the fun part. Select it, and right click to choose Create Component from Artwork > Data List. Double click the resulting Data List component to enter Edit In Place. Select the image, and choose Convert to Data List Part > Repeated Item. Whew. We've got our Data List.

While still in Edit In Place, select your DataList and take a peek under the Layout section of the properties inspector.

<a href="http://flashcats.net/wp-content/uploads/2010/07/datagroup-properties.png" rel="lightbox[341]"><img class="aligncenter size-full wp-image-343" title="Repeated Item Properties" src="http://flashcats.net/wp-content/uploads/2010/07/datagroup-properties.png" alt="" width="175" height="277" /></a>

<a href="http://flashcats.net/wp-content/uploads/2010/07/datagroup-properties.png" rel="lightbox[341]"></a>We want a horizontal list, from left to right, rather than from top to bottom, so select Horizontal layout. Also set the padding and spacing to 0, to make sure that all of your items line up right next to each other. The result of this will be a horizontal list of images, with no spacing between them. The list may look a bit funny, however, because the Repeated Item, which displays the set of your images, still has its bounds set up for your old vertical list.

<a href="http://flashcats.net/wp-content/uploads/2010/07/horizontal-list-layout.png" rel="lightbox[341]"><img class="aligncenter size-full wp-image-344" title="Newly Horizontal Layout" src="http://flashcats.net/wp-content/uploads/2010/07/horizontal-list-layout.png" alt="" width="200" height="298" /></a>

We want to fix this to display only one image at a time. Resize the Repeated Item to exactly fit the first of your images. The little blue bounding box should look like it is framing your first image.

Next up, let's get all of your images into the image gallery. Open up the design time data panel in the lower left corner of Catalyst. You might have to double click the tab that says "Design Time Data."

<a href="http://flashcats.net/wp-content/uploads/2010/07/design-time-data.png" rel="lightbox[341]"><img class="aligncenter size-full wp-image-345" title="Design Time Data" src="http://flashcats.net/wp-content/uploads/2010/07/design-time-data.png" alt="" width="270" height="244" /></a>

Each one of the rows in this panel corresponds to an image you will display in your final gallery. The images will also be shown in the order given here. To add more images, click "Add Row." To remove a row, select it and click the garbage can.

Now to add some scrolling action to your image gallery. Drag out two buttons from the wireframe components panel. Label one "Next" and the other "Previous". Select the two buttons and convert them to a horizontal scrollbar. Edit the scrollbar and assign the Previous button to the left button part, and the Next button to the right button part. I know the thumb and track parts have "required" listed next to them, but that's really more of a suggestion, so don't let it cause you any anxiety.

If you run your project now, you'll have a horizontal list of images you can scroll with the Previous and Next buttons. But, the images will slowly move left and right. We'd like to skip to the next or previous image, without seeing the images painstakingly float across the screen. So exit Edit In Place on the scrollbar. Select the scrollbar, and check out the Component Properties area in the Properties Inspector.

<a href="http://flashcats.net/wp-content/uploads/2010/07/properties-scrollbar.png" rel="lightbox[341]"><img class="aligncenter size-full wp-image-346" title="Scrollbar Properties" src="http://flashcats.net/wp-content/uploads/2010/07/properties-scrollbar.png" alt="" width="200" height="290" /></a>

Here's where we need to do some math. I know its hard, but bear with me. Set the maximum to the number of images in your gallery, and the step size to 1. Whew. Hard work, eh?

Do any final tweaking you'd like, and then give your project a run. You should wind up with something like the following.

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/datalist-slideshow/Main.swf" width="200" height="200" targetclass="flashmovie"]

[![Get Adobe Flash player][1]][2]

[/kml_flashembed]

Hope you all had fun folks!

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer