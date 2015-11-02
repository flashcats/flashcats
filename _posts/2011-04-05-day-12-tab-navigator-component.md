---
title: 'Day 12: Tab Navigator Component'
author: bear
layout: post
permalink: /2011/04/05/day-12-tab-navigator-component/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Custom Skinnable Components
---
And one more makes twelve! Hurray!

This component is pretty simple, buttons 1-10 that, when clicked, navigate through pages 1-10. They also disable the button for the current page, so the component acts like a combination of a tab bar and content. The bonus here is not having to wire up all those "On Click > Go To State > When In State" interactions for each button.

Click on the image for a preview.

[<img class="aligncenter size-full wp-image-572" title="TabNavigator" src="http://flashcats.net/wp-content/uploads/2011/04/TabNavigator.png" alt="" width="385" height="378" />][1]

The FXP is available [here][2].

Details after the jump.

<!--more-->Component States: Pages 1-10

Component Parts: Buttons 1-10

Clicking on a button jumps to the corresponding page and disables the button. All other buttons are enabled. I figured most people should be satisfied with the 10 pages / states built in, but you could always add some more by modifying the skinnable component in Builder.

 [1]: /static/skinnable-tab-navigator/TabNavigator.swf
 [2]: http://dl.dropbox.com/u/21428091/TabNavigator.fxp