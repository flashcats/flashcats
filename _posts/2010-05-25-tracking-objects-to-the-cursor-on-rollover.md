---
title: Tracking objects to the cursor on rollover
author: tarajane
layout: post
permalink: /2010/05/25/tracking-objects-to-the-cursor-on-rollover/
aktt_notify_twitter:
  - no
categories:
  - Catalyst Hacks
  - Interactions
  - Moderate
  - Timeline
---
This post stems from a desire to 'track a visual object to the mouse' in Catalyst on rollover.  
What does that mean exactly?  
It means an object animates such that it appears to be following the mouse cursor.

I wanted to create a dodgeball game prototype in Catalyst, whereby the dodgeball hovered on the bottom of the screen, and followed the mouse horizontally. 

On click, the dodgeball would animate and appear to bounce and hit a player.

You can achieve this mouse tracking behavior using either action sequences, or state transitions.

In this post, I'll discuss how to achieve this using action sequences.

The final outcome, should look like this:  
[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="http://flashcats.net/wp-content/uploads/2010/05/Main1.swf" width="600" height="350" targetclass="flashmovie"]

[![Get Adobe Flash player][1]][2]

[/kml_flashembed]

<!--more-->

1) Draw a rectangle. I chose dimensions of 80x80.  
2) Set the opacity of the rectangle to 0 in the properties panel.  
3) Select the rectangle, and choose 'Convert to component->Button'.  
4) Select the button (you may have to use the layers panel, since the button is invisible), copy, and paste it 8 times (for a total of nine buttons).  
5) I used guides to help align my nine buttons into a grid, as seen below:

<a href="http://flashcats.net/wp-content/uploads/2010/05/Picture-8.png" rel="lightbox[64]"><img src="http://flashcats.net/wp-content/uploads/2010/05/Picture-8-300x281.png" alt="" title="mouseTracking_buttonsGrid" width="300" height="281" class="aligncenter size-medium wp-image-66" /></a>

6) Draw a large circle, and give it some color (I picked a blue outline and fill).  
7) Select the top left most button in your grid.  
8 ) In the Interactions Panel, click +Add Interaction  
9) Select 'On Roll Over' and then 'Play Action Sequence'... click OK [see interaction screenshot below]

<a href="http://flashcats.net/wp-content/uploads/2010/05/Picture-9.png" rel="lightbox[64]"><img src="http://flashcats.net/wp-content/uploads/2010/05/Picture-9-150x150.png" alt="" title="mouseTracking_interaction" width="150" height="150" class="aligncenter size-thumbnail wp-image-67" /></a>

10) The Timeline panel will now be given focus, and you'll see a new action sequence in the list.  
11) Select the circle you drew, and click the 'Add Action' button in the bottom button bar of the Timelines panel.  
12) Click 'Move'. This will create a move effect on the circle when we roll over the button.  
13) Now look in the properties panel. You'll see a bunch of properties we can set on this move effect.  
14) Set them up to match the screenshot below. Note that your X, Y numbers vary depending where you placed the grid on the artboard. To figure out the X, Y, move your circle such that it is over the button, look at the X, Y in the properties panel, reselect the action sequence in the timeline panel, and then enter your correct coordinates.  
<a href="http://flashcats.net/wp-content/uploads/2010/05/Picture-10.png" rel="lightbox[64]"><img src="http://flashcats.net/wp-content/uploads/2010/05/Picture-10-220x300.png" alt="" title="mouseTracking_moveEffect" width="220" height="300" class="aligncenter size-medium wp-image-68" /></a>

15) Repeat steps 7 through 14 for each button in your grid. When you're done, you should have nine interactions (one rollover per button), nine action sequences (one per button), each with its own move effect  
16) Run your project. When you mouse over each button in the invisible grid, your circle should move and 'follow' the mouse.

You can take this a step further, and when editing the 'move effect bars' in the properties panel, change the easing.

We'll post on easing effects later, but for now here's the same example as above, but with an 'elastic' effect applied.

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="http://flashcats.net/wp-content/uploads/2010/05/Main2.swf" width="600" height="350" targetclass="flashmovie"]

[![Get Adobe Flash player][1]][2]

[/kml_flashembed]

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer