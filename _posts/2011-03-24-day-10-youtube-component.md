---
title: 'Day 10: YouTube Component'
author: bear
layout: post
permalink: /2011/03/24/day-10-youtube-component/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Custom Skinnable Components
tags:
  - Custom Skinnable Components
  - youtube
---
I've seen a couple requests for embedding YouTube videos in Flash Catalyst projects. This skinnable component pulls in a YouTube video at runtime, using a video id and the YouTube AS3 API.

Click the image to view the running example.

[<img class="aligncenter size-full wp-image-557" title="YouTube Preview" src="http://flashcats.net/wp-content/uploads/2011/03/YouTubePreview.png" alt="" width="400" height="295" />][1]

You can download the FXP [here][2],  
Or the FXPL [here][3].

More details after the jump.

<!--more-->The skinnable component takes a group placeholder to insert the player into at runtime. It also takes a video id as a RichText part. The video id should be the last 11 characters of a YouTube video url, right after the "=" sign. The video id should go in the "Properties" state, and the placeholder should go in the "Video" state. If there is a problem, the skin will wind up in the "Error" state, with the problem in the error message skin part, if it's assigned.

It sounds a little complicated, but you can always check out how the FXP is set up.

 [1]: /static/skinnable-youtube/YouTubeProject.swf
 [2]: http://dl.dropbox.com/u/21428091/YouTube.fxp
 [3]: http://dl.dropbox.com/u/21428091/YouTubeLib.fxpl