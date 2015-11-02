---
title: 'Day 1: Fullscreen Button'
author: bear
layout: post
permalink: /2010/12/01/day-1-fullscreen-button/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Custom Skinnable Components
  - Moderate
---
If any of you tried to make fullscreen applications in Flash Catalyst 1.0, you know that there was some tinkering necessary in Builder. While it's a great way to get your feet wet with Flex, sometimes you'd like something easier. So, I present to you, the Fullscreen Button Component as the first skinnable component of Christmas! Just skin the button, specify the button to make your application go fullscreen, and the skinnable component will handle the rest.

[kml_flashembed publishmethod="dynamic" fversion="10.1.0" movie="/static/fullscreen-button/Main.swf" width="200" height="200" targetclass="flashmovie" allowfullscreen="true"]

[![Get Adobe Flash player][1]][2]

[/kml_flashembed]

So let's get cooking!

<!--more-->You'll need the preview release of Panini, and the FXPL containing the skinnable component, in a .zip file 

[here][3].

This time, you can just unzip the file and import the FXPL via File > Import > Library Package, or the library panel. Skinning the component should follow the same steps outlined in this [previous post][4].

One final caveat, you will need to enable fullscreen mode on the Flash Player when you embed your .swf. You can read a bit more in [this article][5], under "Enabling full-screen mode in Flash Player".

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer
 [3]: http://flashcats.net/static/fullscreen-button/FullscreenLibrary.fxpl.zip
 [4]: flashcats.net/2010/11/09/using-custom-skinnable-components-in-panini/
 [5]: http://help.adobe.com/en_US/ActionScript/3.0_ProgrammingAS3/WS2E9C7F3B-6A7C-4c5d-8ADD-5B23446FBEEB.html