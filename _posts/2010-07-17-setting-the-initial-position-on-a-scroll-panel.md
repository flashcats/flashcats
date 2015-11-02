---
title: Setting the initial position on a scroll panel
author: bear
layout: post
permalink: /2010/07/17/setting-the-initial-position-on-a-scroll-panel/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Interactions
  - Moderate
  - Wireframe Components
---
If you've been playing around with scroll panels, you've probably noticed that the scrolling content window always starts off displaying the upper left corner of the actual scrolling content. Great for anything text-based, but not so great for anything image-based. For example, if you're scrolling an image, you will probably want to start out with the content window displaying the center of your content.

### Example 1 (Centered Content)

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/scrollpanel-initial-position/Main.swf" width="200" height="200" targetclass="flashmovie"]

[![Get Adobe Flash player][1]][2]

[/kml_flashembed]

### Example 2 (Default, Top-left Content)

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/trackless-scrollbar/Main.swf" width="200" height="200" targetclass="flashmovie"]

[![Get Adobe Flash player][1]][2]

[/kml_flashembed]

More after the jump!

<!--more-->

Of course, pay no attention to me reusing a project (hey, they take time!). The underlying mechanism here is pretty simple, and is quite similar to the [trick for getting scroll panels to reset][3].

### Here's what you do

  1. Create a scroll panel with scroll bar(s) to scroll its content.
  2. In Edit-In-Place on the scroll panel, select the scroll bars in the scroll panel's "Normal" state.
  3. In the Properties Inspector (lower right), under component, notice the minimum, maximum, and value for the scroll bars. These represent the range of numeric values a scrollbar can go through as it scrolls your content. For centering your content, set the value properties to half the maximum.
  4. In the scroll panel's "Disabled" state, set the scrollbars' value properties to 1. The number here doesn't matter, it just has to be non-zero, and not equal to the value in the "Normal" state.
  5. Exit edit in place, click on an empty area to deselect everything.
  6. Add an On Application Start > Play Action Sequence interaction.
  7. For your action sequence, add a set property > disabled action for the scroll panel. To do this, select the scroll panel in the artboard, then select the On Application Start action sequence in the timeline. Choose Add Action > Set Property > Enabled > False (the enabled false bit happens in the Properties Inspector to the right).
  8. Create a second set property action slightly after the first, and  have it set enabled to true.
  9. You're done!

The way this works is by switching between the normal and disabled states on the scroll panel. When switching to the disabled state, the scroll bars have a new position, and the new position changes the location of the scrolling content. Switching back to the normal state sets the scrollbars' positions again, which changes the location of the scrolling content one more time.

So why doesn't just setting the initial value of the scrollbars do the trick? Because they're not wired up to scroll the content until **after** the initial value is set. Which means you can set the value, but it's not going to scroll the content because the scrollbar isn't ready to scroll the content just yet.

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer
 [3]: http://flashcats.net/2010/06/15/statefulness/