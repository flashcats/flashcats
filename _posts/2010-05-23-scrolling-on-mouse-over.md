---
title: Scrolling on Mouse Over
author: bear
layout: post
permalink: /2010/05/23/scrolling-on-mouse-over/
aktt_notify_twitter:
  - no
categories:
  - Catalyst Hacks
tags:
  - Interactions
  - mouse over
  - scroll
---
In Flash Catalyst, you can drop scroll bars in a Scroll Panel, and they will automatically scroll the content for you. The scrollbars will scroll the content whenever someone clicks on the scroll buttons or drags the scrollbar thumb. But what if you want the content to scroll when someone mouses over a scroll button? Well, there's a way to wire that up, too (and an example, after the jump).

<!--more-->

### The Example

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/autoscroll/Main.swf" width="400" height="400" targetclass="flashmovie"][![Get Adobe Flash player][1]][2]

[/kml_flashembed]

### What you'll need to get started

  1. The content you want to scroll
  2. The button(s) you want to cause the scrolling
  3. A video asset that plays for a short duration (we're going to use it as a timer)

### Here's how to make it work

  1. Take the content you want to scroll and convert it to a custom component. This'll just make moving it easier.
  2. Create one of your scroll buttons, and create an instance of the video you're using as a timer.
  3. Create an on mouse over interaction that starts the video, and an on mouse out interaction that stops it.
  4. Click the video, set it to "Loop" in the properties panel.
  5. In the interactions panel, add an on video play complete action sequence.
  6. In the timelines panel, add an action to your video play complete action sequence that moves your scrolling content. This move action corresponds to what should happen between your video timer "ticks". It should be just longer than your video, and have linear easing with zero ease-in and zero ease-out. This will make the scrolling less jerky.
  7. Repeat steps 2-6 for each scroll button you want.
  8. Add any extra chrome.

Check out this nifty diagram:

<a href="http://flashcats.net/wp-content/uploads/2010/05/autoscrolldiagram2.png" rel="lightbox[51]"><img class="aligncenter size-medium wp-image-56" title="Mouse Over Scroll Diagram" src="http://flashcats.net/wp-content/uploads/2010/05/autoscrolldiagram2-300x269.png" alt="" width="300" height="269" /></a>

### Some caveats

  * This repeats a "Move" action, so there's going to be a bit of jerkiness
  * Try to use a short video asset with a small file size, or your project may become overly large
  * There are some focus issues, where the mouse out event isn't always triggered on the button.

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer