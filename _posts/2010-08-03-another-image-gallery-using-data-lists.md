---
title: Another Image Gallery Using Data Lists
author: bear
layout: post
permalink: /2010/08/03/another-image-gallery-using-data-lists/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Interactions
  - Moderate
  - Wireframe Components
tags:
  - data list
  - image gallery
  - slideshow
  - transitions
---
You know what they say, there's more than one way to skin a Data List. And there's certainly more than one way to build an image gallery in Flash Catalyst. The first method was covered in this [previous post][1]. This time, however, we're going to create one with transitions between images. Nifty, right? More after the jump!

<!--more-->This method basically uses a film strip of images which we slide underneath a clipping window. We only see one image at a time, but the filmstrip is just moving from left to right as we progress through the images.

To start off, you'll want a bunch of images, all with similar dimensions and aspect ratios. Import them all into Catalyst. Drag one image out to the artboard from the Library Panel, position and size it as a placeholder for the current image in your image gallery. We're going to turn this image into our film strip using a Data List. Select the image and choose Convert Artwork to Component > Data List using the HUD, or the right-click context menu. The result should be as follows.

<a href="http://flashcats.net/wp-content/uploads/2010/08/imagedatalist.png" rel="lightbox[392]"><img class="aligncenter size-full wp-image-393" title="imagedatalist" src="http://flashcats.net/wp-content/uploads/2010/08/imagedatalist.png" alt="" width="270" height="268" /></a>

Double click the Data List to enter Edit In Place mode. Select the image and choose Convert To Data List Part > Repeated Item from the HUD or right click menus. In the Layout section, set the list to have horizontal layout, and 0 spacing. If that sounds confusing, check out the [previous image gallery post][1] for more details.

In the Properties Inspector, adjust the Repeated Item positioning and dimensions. It should be positioned at the origin (0, 0), with width and height enough to display all of your images. I was using five 200x150 pixel images, and so my Repeated Item had a width of 1000 and a height of 150. This is what my Data List looked like.

<a href="http://flashcats.net/wp-content/uploads/2010/08/filmstriplist.png" rel="lightbox[392]"><img class="aligncenter size-full wp-image-395" title="Film Strip Data List" src="http://flashcats.net/wp-content/uploads/2010/08/filmstriplist.png" alt="" width="600" height="103" /></a>Next up, we have to create the viewing window for our film strip Data List, that slides the list underneath. To do this, exit edit in place on the Data List. Select it in artboard, and convert it to a Custom / Generic Component with right click Convert Artwork to Component > Custom / Generic Component command. Double click to edit the new component. Add 2 buttons to help browse your gallery, a "next" and "previous" button.

Now we need to clip the component to display only the current image (none of the previous or subsequent images). Right click, and deselect "Auto size component bounds". Right click again, and select "Clip to component bounds". This will allow us to manually set the bounds of our custom component, and, furthermore, make sure we don't display anything outside those bounds. You'll notice some black crosshairs marking the component's manual bounds. Drag them so that they show only a single image, and the next and previous buttons. My setup looked like this.

<a href="http://flashcats.net/wp-content/uploads/2010/08/imagesandbuttons.png" rel="lightbox[392]"><img class="aligncenter size-full wp-image-397" title="Viewer Window Component" src="http://flashcats.net/wp-content/uploads/2010/08/imagesandbuttons.png" alt="" width="600" height="227" /></a>

All that's left is to add the interactions that move the filmstrip around. Select the "Next" button, and create an On Click > Play Action Sequence interaction. In the Timeline, select the On Click Action Sequence and the Data List, then choose Add Action > Move to add a move action to the action sequence. When clicking the "Next" button, you want the film strip to move to the left the width of one image, so in the Properties Inspector, I set the move to Relative > x: -200, y: 0. I added an opposite move action sequence to the "Previous" button. The result?

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/datalist-slideshow-2/Main.swf" width="300" height="300" targetclass="flashmovie" base="/static/datalist-slideshow-2/"]

[![Get Adobe Flash player][2]][3]

[/kml_flashembed]

Note: Make sure you add the move action to the data list, and not the button, or you'll have your buttons flying across the screen!

You could, of course, add some more complex actions to the action sequence for more interesting effects. For example, creating a fade between transitioning images. The weakness of this method as opposed to the [previous one][1] is that the buttons will continue to scroll the film strip, even after you've passed beyond the first or last image. Something to watch out for.

 [1]: http://flashcats.net/2010/07/26/creating-an-image-gallery-using-a-data-list/
 [2]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [3]: http://adobe.com/go/getflashplayer