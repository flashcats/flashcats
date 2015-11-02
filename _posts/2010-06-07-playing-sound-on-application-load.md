---
title: Playing sound on application load
author: tarajane
layout: post
permalink: /2010/06/07/playing-sound-on-application-load/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Catalyst Hacks
  - Interactions
  - Moderate
---
Although I'm not a huge fan of websites where audio begins to play immediately on application load, I wanted to try and accomplish the effect in Catalyst.

Just be sure to keep a mute or stop button front and center for your users. <img src='http://localhost:8888/flashcats_wp/wp-includes/images/smilies/icon_wink.gif' alt=';)' class='wp-smiley' /> 

We're going to use the Adobe Media Encoder to convert the audio file to a video file.

Why? Well Catalyst offers extremely limited support with audio files in 1.0. We can play them, but otherwise cannot control them (pause, stop). The video support offers much better options for controlling content.

First, choose the audio file you'd like to being immediately playing on application launch.  
<!--more-->

Open Adobe Media Encoder CS5 (ships with Flash Catalyst).

Drag in your mp3 file, and make sure the output is f4v.

Click start, and it'll encode your mp3 file to an f4v file and output it to the same directory as the original mp3.

Lets leave Media Encoder.

Open Flash Catalyst.

1) From the file menu, select Import Video  
2) Navigate and choose the video file you \*just\* encoding.  
3) Click ok. A blank (black screen) video will be created on the artboard.  
4) With the video selected, in the properties panel, set the opacity to 0.  
5) Additionally, in the layers panel, make sure the video is the bottom most thing in the layers panel. We want it sit behind all of your content and not interfere with mouse interactions.  
6) Click anywhere on the gray area outside the artboard, such that nothing is selected anymore.  
7) The interactions panel should say "Application"  
8 ) Click 'Add Interaction', and choose 'play video', and select your video file from the list of available videos (if you imported one video, there should only be one listed).  
<a href="http://flashcats.net/wp-content/uploads/2010/06/appStartInteraction.png" rel="lightbox[124]"><img src="http://flashcats.net/wp-content/uploads/2010/06/appStartInteraction-246x300.png" alt="" title="appStartInteraction" width="246" height="300" class="aligncenter size-medium wp-image-126" /></a>

Now when your application loads, it will begin playing your sound file right away.

To mute, or pause your video, you can create play/mute buttons like I have shown below:  
[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/playAudioOnAppStart/deploytoweb/Main.swf" width="400" height="60" targetclass="flashmovie"]

[![Get Adobe Flash player][1]][2]

[/kml_flashembed]

I will cover how to make these play/mute toggle button control in a future post.

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer