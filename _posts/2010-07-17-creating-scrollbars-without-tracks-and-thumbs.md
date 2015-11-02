---
title: Creating Scrollbars without Tracks and Thumbs
author: bear
layout: post
permalink: /2010/07/17/creating-scrollbars-without-tracks-and-thumbs/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Easy
  - Wireframe Components
tags:
  - parts
  - scrollbars
  - thumb
  - track
---
Have you ever designed a scroll panel or data list and wanted to make it scroll with just buttons? For example, the scroll panel below scrolls its content with just an up, down, left, and right button.

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/trackless-scrollbar/Main.swf" width="200" height="200" targetclass="flashmovie"]  
[![Get Adobe Flash player][1]][2]  
[/kml_flashembed]

Normally, when you create a scrollbar, Catalyst prompts you to assign the thumb and track for each scrollbar. In fact, they are both marked, rather ominously, as "required". One way of getting around this is to create the thumb and track parts, and then hide them, either offscreen, or setting their opacity to zero. But this can leave weird mouse interaction areas in your swf, and it's less than ideal.

As it turns out, "required" parts for the horizontal and vertical scrollbars are really only suggested. They're part of a typical scrollbar, but in this case, we don't want a typical scrollbar. So guess what? You don't have to assign them. Just assign the button parts (left, right, up, down) and you're good to go.

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer