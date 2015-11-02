---
title: Going Fullscreen
author: bear
layout: post
permalink: /2010/06/09/going-fullscreen/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Advanced
  - Builder Tweaks
tags:
  - builder
  - fullscreen
  - scale
---
All the cool kids are building applications that go fullscreen, now you can too! To accomplish this, you'll need to get your hands dirty in Builder and write some ActionScript code. But, when you're done, you'll have a .swf like the one below.

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/swf-fullscreen/Main.swf" width="300" height="300" targetclass="flashmovie" allowfullscreen="true"]

[![Get Adobe Flash player][1]][2]  
[/kml_flashembed]

<!--more-->

### Update

If you have Catalyst CS 5.5 or later, I would highly recommend using constraints coupled with a custom skinnable component (like [this one][3]) that drives the full screen behavior. For an introduction to custom skinnable components, check out [this post][4].

### What you'll need

  1. A Catalyst project you'll want to make full screen
  2. Flash Catalyst and Flash Builder

### What to do

  1. Open your project in Catalyst. Create a button you would like to transition between regular and fullscreen modes.
  2. Add a goto url interaction to the button. For this example we'll set the url to *foobar.com*.
  3. Save your project. Open Builder and import it (File > Import FXP).
  4. Open the Main.mxml file. You should see a <code class="codecolorer text default">&lt;span class="text">&lt;fx:Script&gt;&lt;/span></code> tag containing the goto url interaction from Catalyst. The interaction (an ActionScript function) will look like:
<div class="wp_syntax">
  <div class="code">
    <pre class="actionscript3" style="font-family:monospace;"><span style="color: #0033ff; font-weight: bold;">protected</span> <span style="color: #339966; font-weight: bold;">function</span> button_clickHandler<span style="color: #000000;">&#40;</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">:</span><span style="color: #0033ff; font-weight: bold;">void</span>
<span style="color: #000000;">&#123;</span>
    <span style="color: #004993;">navigateToURL</span><span style="color: #000000;">&#40;</span> <span style="color: #0033ff; font-weight: bold;">new</span> <span style="color: #004993;">URLRequest</span><span style="color: #000000;">&#40;</span>
        <span style="color: #004993;">encodeURI</span><span style="color: #000000;">&#40;</span><span style="color: #990000;">"http://foobar.com"</span><span style="color: #000000;">&#41;</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">,</span> <span style="color: #990000;">"_self"</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">;</span>
<span style="color: #000000;">&#125;</span></pre>
  </div>
</div>

  5. Delete the whole block and copy-paste the following code snippet. If your function from above was named something other than <code class="codecolorer text default">&lt;span class="text">button_clickHandler&lt;/span></code>, rename the below function to match (you'll probably only need to append a number).
<div class="wp_syntax">
  <div class="code">
    <pre class="actionscript3" style="font-family:monospace;"><span style="color: #0033ff; font-weight: bold;">protected</span> <span style="color: #339966; font-weight: bold;">function</span> button_clickHandler<span style="color: #000000;">&#40;</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">:</span><span style="color: #0033ff; font-weight: bold;">void</span> <span style="color: #000000;">&#123;</span>
    toggleFullScreen<span style="color: #000000;">&#40;</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">;</span>
<span style="color: #000000;">&#125;</span>
&nbsp;
<span style="color: #0033ff; font-weight: bold;">private</span> <span style="color: #339966; font-weight: bold;">function</span> toggleFullScreen<span style="color: #000000;">&#40;</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">:</span><span style="color: #0033ff; font-weight: bold;">void</span> <span style="color: #000000;">&#123;</span>
    <span style="color: #6699cc; font-weight: bold;">var</span> newState<span style="color: #000066; font-weight: bold;">:</span><span style="color: #004993;">String</span><span style="color: #000066; font-weight: bold;">;</span>
    <span style="color: #0033ff; font-weight: bold;">if</span> <span style="color: #000000;">&#40;</span><span style="color: #004993;">stage</span><span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">displayState</span> == StageDisplayState<span style="color: #000066; font-weight: bold;">.</span>FULL_SCREEN<span style="color: #000000;">&#41;</span>
        newState = StageDisplayState<span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">NORMAL</span><span style="color: #000066; font-weight: bold;">;</span>
    <span style="color: #0033ff; font-weight: bold;">else</span>
        newState = StageDisplayState<span style="color: #000066; font-weight: bold;">.</span>FULL_SCREEN<span style="color: #000066; font-weight: bold;">;</span>
&nbsp;
    <span style="color: #0033ff; font-weight: bold;">try</span> <span style="color: #000000;">&#123;</span>
        <span style="color: #004993;">stage</span><span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">displayState</span> = newState<span style="color: #000066; font-weight: bold;">;</span>
    <span style="color: #000000;">&#125;</span> <span style="color: #0033ff; font-weight: bold;">catch</span> <span style="color: #000000;">&#40;</span>any<span style="color: #000066; font-weight: bold;">:*</span><span style="color: #000000;">&#41;</span> <span style="color: #000000;">&#123;</span>
        <span style="color: #009900; font-style: italic;">//ignore</span>
    <span style="color: #000000;">&#125;</span>
<span style="color: #000000;">&#125;</span></pre>
  </div>
</div>

  6. Publish your project (Project > Export Release Build). Make sure to set the "Export to Folder" to a convenient location.

And that's it, you're all set!

### Notes

When you embed your swf in HTML, you will need to allow it to go full screen. This will look something like setting allowFullscreen="true" in an object or embed tag. You can learn more [here][5].

The above code just resizes the Flash stage to fullscreen. If you want your application to scale, you'll need to follow the same steps outlined in the previous post: [Making a Catalyst Swf Scalable][6].

Once you open your project in Builder, you will no longer be able to edit it in Catalyst. You can, however, copy-paste code from Catalyst's code view into your project, or reimport Catalyst FXP(L)s.

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer
 [3]: http://flashcats.net/2010/12/01/day-1-fullscreen-button/
 [4]: http://flashcats.net/2010/11/09/using-custom-skinnable-components-in-panini/
 [5]: www.adobe.com/devnet/flashplayer/articles/full_screen_mode.html
 [6]: http://flashcats.net/2010/06/08/making-a-catalyst-swf-scalable/