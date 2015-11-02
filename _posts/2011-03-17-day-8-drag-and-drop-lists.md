---
title: 'Day 8: Drag and Drop Lists'
author: tarajane
layout: post
permalink: /2011/03/17/day-8-drag-and-drop-lists/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Custom Skinnable Components
---
I decided to whip a simple custom skinnable component to enable drag and drop between lists. I've posted a quick sample skin of how this might look in a 'these are a few of my favorite things' drag/drop scenario, which allows a user to drag from a source list to a target list. 

Check it out by clicking on the image below:

[<img src="http://flashcats.net/wp-content/uploads/2011/03/Screen-shot-2011-03-17-at-10.07.34-PM-300x112.png" alt="" title="FavoriteThings_DragDrop" width="300" height="112" class="aligncenter size-medium wp-image-525" />][1]

Download the FXP [here][2].  
Download the FXPL [here][3].

More info after the jump.

<!--more-->

You can customize three states of the list: 

  * **normal** (or default)
  * **dragOver** (what it looks like while a user is dragging on top of a list which supports drop)
  * **drop **(which is how the list appears for 0.5 seconds after releasing the mouse cursor over a drop-able list). 

There are some optional skin parts on the DragDropList which you can assign to customize lists: 

  * **enableDrag** - text part which you can set as true or false. If true, allow dragging from the list.
  * **enableDrop** - text part which you can set as true or false. If true, allow dropping onto the list.
  * **enableDragMove** - text part which you can set as true or false. If true, remove the item from the source list after dropping onto a target list. If false, copy items from the source list to the target list.

In our example above, the left list of favorite things only allows you to drag. The right list only allows you to drop. You'll notice after dragging and dropping an item from the left to right, the item stays in the left list. We set enableDragMove to false, just in case you're so passionate about vinyl it needs to be in your favorite things list more than once.

You can customize your list items to look however you'd like... so drag and drop lists of text, images, graphics, etc.

 [1]: /static/drag-and-drop-list/deploy-to-web/DragAndDrop.swf
 [2]: http://dl.dropbox.com/u/6790579/DragAndDrop.fxp
 [3]: http://dl.dropbox.com/u/6790579/DragAndDropList.fxpl