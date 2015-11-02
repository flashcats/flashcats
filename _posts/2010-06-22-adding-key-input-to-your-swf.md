---
title: Adding key input to your swf
author: bear
layout: post
permalink: /2010/06/22/adding-key-input-to-your-swf/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Builder Tweaks
  - Interactions
  - Moderate
tags:
  - builder
  - Interactions
  - key press
---
In Catalyst, it's easy to mock up interactions using mouse events with buttons and other components. But what if you want to add keyboard interactions, for events like pressing the "j" or enter keys? For example, try clicking the button in the below swf. Notice that you can also press the spacebar or the right arrow key to get the same effect.

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/key-handler/Main.swf" width="200" height="200" targetclass="flashmovie"]

[![Get Adobe Flash player][1]][2]

[/kml_flashembed]

The easiest way to do this is to mock up your interactions using buttons in Catalyst, and then tweak your project in Builder to add the key events. We'll go over how to do this after the jump.

<!--more-->First of all, create your project in Catalyst. Create a button and a corresponding interaction to prototype your key interactions. For example, in the above swf, the button on click interaction was a mockup for the eventual spacebar and arrow key interactions. For this tutorial, we're going to assume that all of your buttons and interactions are in your top level application.

Save your project out as an FXP, and import it into Flash Builder via the File > Import FXP menu item. Using the default import options should work just fine. Open up the "Main.mxml" file. The easiest way to do this is probably with the Package Explorer to the left. Now we're going to insert a little bit of code.  
<a href="http://flashcats.net/wp-content/uploads/2010/06/key-handler-builder.png" rel="lightbox[237]"><img class="aligncenter size-medium wp-image-249" title="Adding the Key Handler in Builder" src="http://flashcats.net/wp-content/uploads/2010/06/key-handler-builder-300x225.png" alt="" width="300" height="225" /></a>

First of all, we're going to adjust the Application tag. Catalyst dumps all of the application attributes on a single line, so I inserted some extra newlines to make them more readable. At the end of the application tag, add the following attribute:

<div class="wp_syntax">
  <div class="code">
    <pre class="actionscript3" style="font-family:monospace;">applicationComplete=<span style="color: #990000;">"init()"</span></pre>
  </div>
</div>

Then, place the following two functions in your script block:

<div class="wp_syntax">
  <div class="code">
    <pre class="actionscript3" style="font-family:monospace;"><span style="color: #0033ff; font-weight: bold;">private</span> <span style="color: #339966; font-weight: bold;">function</span> <span style="color: #004993;">init</span><span style="color: #000000;">&#40;</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">:</span><span style="color: #0033ff; font-weight: bold;">void</span> <span style="color: #000000;">&#123;</span>
    <span style="color: #004993;">stage</span><span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">addEventListener</span><span style="color: #000000;">&#40;</span><span style="color: #004993;">KeyboardEvent</span><span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">KEY_DOWN</span><span style="color: #000066; font-weight: bold;">,</span> reportKeyDown<span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">;</span>
<span style="color: #000000;">&#125;</span>
<span style="color: #0033ff; font-weight: bold;">private</span> <span style="color: #339966; font-weight: bold;">function</span> reportKeyDown<span style="color: #000000;">&#40;</span>event<span style="color: #000066; font-weight: bold;">:</span><span style="color: #004993;">KeyboardEvent</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">:</span><span style="color: #0033ff; font-weight: bold;">void</span> <span style="color: #000000;">&#123;</span>
    <span style="color: #6699cc; font-weight: bold;">var</span> keyPressed<span style="color: #000066; font-weight: bold;">:</span><span style="color: #004993;">String</span> = <span style="color: #004993;">String</span><span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">fromCharCode</span><span style="color: #000000;">&#40;</span>event<span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">charCode</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">;</span>
    <span style="color: #0033ff; font-weight: bold;">if</span> <span style="color: #000000;">&#40;</span>keyPressed == <span style="color: #990000;">' '</span><span style="color: #000000;">&#41;</span> button_clickHandler<span style="color: #000000;">&#40;</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">;</span>
<span style="color: #000000;">&#125;</span></pre>
  </div>
</div>

You will need to tweak two parts of the reportKeyDown function.

  1. Change the character inside the single quotes to the character you would like to trigger the interaction.
  2. Change button_clickHandler() to the function that matches the proper button click interaction. If you find the button that corresponds to your key press in the mxml file, the "click" attribute will list the function name.

If your key press is a control key, meaning it doesn't correspond to a specific letter on the keyboard, try using a variation of the following code snippet instead. It would replace the lines inside reportKeyDown.

<div class="wp_syntax">
  <div class="code">
    <pre class="actionscript3" style="font-family:monospace;"><span style="color: #0033ff; font-weight: bold;">if</span> <span style="color: #000000;">&#40;</span>event<span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">keyCode</span> == <span style="color: #004993;">Keyboard</span><span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">RIGHT</span><span style="color: #000000;">&#41;</span> button_clickHandler<span style="color: #000000;">&#40;</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">;</span></pre>
  </div>
</div>

And that's about it. The top of your Main.mxml file should now look something like this.

<div class="wp_syntax">
  <div class="code">
    <pre class="actionscript3" style="font-family:monospace;"><span style="color: #000066; font-weight: bold;">&lt;?</span>xml <span style="color: #004993;">version</span>=<span style="color: #990000;">"1.0"</span> encoding=<span style="color: #990000;">"utf-8"</span><span style="color: #000066; font-weight: bold;">?&gt;</span>
<span style="color: #000066; font-weight: bold;">&lt;</span>s<span style="color: #000066; font-weight: bold;">:</span>Application xmlns<span style="color: #000066; font-weight: bold;">:</span>fx=<span style="color: #990000;">"http://ns.adobe.com/mxml/2009"</span>
                xmlns<span style="color: #000066; font-weight: bold;">:</span>s=<span style="color: #990000;">"library://ns.adobe.com/flex/spark"</span>
                xmlns<span style="color: #000066; font-weight: bold;">:</span><span style="color: #004993;">d</span>=<span style="color: #990000;">"http://ns.adobe.com/fxg/2008/dt"</span>
                xmlns<span style="color: #000066; font-weight: bold;">:</span>fc=<span style="color: #990000;">"http://ns.adobe.com/flashcatalyst/2009"</span>
                <span style="color: #004993;">backgroundColor</span>=<span style="color: #990000;">"#FFFFFF"</span> <span style="color: #004993;">height</span>=<span style="color: #990000;">"200"</span>
                preloaderChromeColor=<span style="color: #990000;">"#FFFFFF"</span> <span style="color: #004993;">width</span>=<span style="color: #990000;">"200"</span>
                applicationComplete=<span style="color: #990000;">"init()"</span><span style="color: #000066; font-weight: bold;">&gt;</span>
    <span style="color: #000066; font-weight: bold;">&lt;</span>fx<span style="color: #000066; font-weight: bold;">:</span>Script<span style="color: #000066; font-weight: bold;">&gt;&lt;!</span><span style="color: #000000;">&#91;</span>CDATA<span style="color: #000000;">&#91;</span>
        <span style="color: #0033ff; font-weight: bold;">private</span> <span style="color: #339966; font-weight: bold;">function</span> <span style="color: #004993;">init</span><span style="color: #000000;">&#40;</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">:</span><span style="color: #0033ff; font-weight: bold;">void</span> <span style="color: #000000;">&#123;</span>
            <span style="color: #004993;">stage</span><span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">addEventListener</span><span style="color: #000000;">&#40;</span><span style="color: #004993;">KeyboardEvent</span><span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">KEY_DOWN</span><span style="color: #000066; font-weight: bold;">,</span> reportKeyDown<span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">;</span>
        <span style="color: #000000;">&#125;</span>
        <span style="color: #0033ff; font-weight: bold;">private</span> <span style="color: #339966; font-weight: bold;">function</span> reportKeyDown<span style="color: #000000;">&#40;</span>event<span style="color: #000066; font-weight: bold;">:</span><span style="color: #004993;">KeyboardEvent</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">:</span><span style="color: #0033ff; font-weight: bold;">void</span> <span style="color: #000000;">&#123;</span>
            <span style="color: #009900; font-style: italic;">// Option 1: Get the key character for character keys</span>
            <span style="color: #6699cc; font-weight: bold;">var</span> keyPressed<span style="color: #000066; font-weight: bold;">:</span><span style="color: #004993;">String</span> = <span style="color: #004993;">String</span><span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">fromCharCode</span><span style="color: #000000;">&#40;</span>event<span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">charCode</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">;</span>
            <span style="color: #0033ff; font-weight: bold;">if</span> <span style="color: #000000;">&#40;</span>keyPressed == <span style="color: #990000;">' '</span><span style="color: #000000;">&#41;</span> button_clickHandler<span style="color: #000000;">&#40;</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">;</span>
            <span style="color: #009900; font-style: italic;">// Option 2: Get the keyboard button for control keys</span>
            <span style="color: #0033ff; font-weight: bold;">if</span> <span style="color: #000000;">&#40;</span>event<span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">keyCode</span> == <span style="color: #004993;">Keyboard</span><span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">RIGHT</span><span style="color: #000000;">&#41;</span> button_clickHandler<span style="color: #000000;">&#40;</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">;</span>
        <span style="color: #000000;">&#125;</span>
        <span style="color: #0033ff; font-weight: bold;">protected</span> <span style="color: #339966; font-weight: bold;">function</span> button_clickHandler<span style="color: #000000;">&#40;</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">:</span><span style="color: #0033ff; font-weight: bold;">void</span>        <span style="color: #000000;">&#123;</span>
            Sequence1<span style="color: #000066; font-weight: bold;">.</span><span style="color: #004993;">play</span><span style="color: #000000;">&#40;</span><span style="color: #000000;">&#41;</span><span style="color: #000066; font-weight: bold;">;</span>
        <span style="color: #000000;">&#125;</span>
    <span style="color: #000000;">&#93;</span><span style="color: #000000;">&#93;</span><span style="color: #000066; font-weight: bold;">&gt;&lt;/</span>fx<span style="color: #000066; font-weight: bold;">:</span>Script<span style="color: #000066; font-weight: bold;">&gt;</span>
    <span style="color: #000066; font-weight: bold;">...</span></pre>
  </div>
</div>

You can keep adding new keys to the reportKeyDown method to call other functions. For example, if you wanted to make the 'j' key do something entirely different. But that's all there is to it.

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer