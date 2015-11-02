---
title: Looping an Action Sequence
author: bear
layout: post
permalink: /2010/05/20/looping-an-action-sequence/
categories:
  - Catalyst Hacks
tags:
  - action sequence
  - loop
  - repeat
---
Sometimes you would like an action sequence to repeat in Flash Catalyst. For example, you might create an animation between two component states that you want to loop. Catalyst doesn't have a "Loop" feature, but there is a workaround.

<!--more-->Say you have a Gear component that you'd like to loop between a "Left" state and a "Right" state.

What you'll need:

  1. A list of actions you want to repeat (we're going to turn this into an action sequence)
  2. A video clip that lasts as long as the action sequence you want to repeat. You'll want it to have as small a file size as possible.

Here's what you do:

  1. Import your video clip into Catalyst, this is going to be the timer for your action sequence.
  2. Place your video clip on the Art Board, and check "Loop" in the Properties Inspector (lower right). If you want to start the action sequence when your application loads, select "Auto Play" as well.
  3. Select your video clip, and in the Interactions Panel (mid right), and add an "On Video Play Complete > Play Action Sequence" interaction.
  4. In the Timelines Panel (bottom), select the "Video Player On Video Play Complete" that you created above.
  5. Add all the actions that you want to be part of your repeating action sequence.
  6. Hide the video by resizing it to be very small and setting its opacity to zero.

Let's have an example!

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/animationloop/Main.swf" width="350" height="150" targetclass="flashmovie"][![Get Adobe Flash player][1]][2]

[/kml_flashembed]

Some caveats:

  * The action sequence will keep playing until the video stops, so you may have to reset everything to its original position before the action sequence repeats.
  * Generally, the best way to factor this is to use the Set State action on a custom component, that you transition from State1 -> State2 -> State1. This means you can organize everything you want to change between your custom components two states.
  * The action sequence won't start until the video has completed. If you want it to start immediately, you'll have to add an extra initial action sequence that copies the first. Another good reason to factor using a custom component.
  * Your published swf won't include the video file, so make sure you place the Catalyst assets folder alongside your Main.swf. You can always just copy the "deploy to web" folder and you'll do just fine.
  * The proper way of creating this effect is through some tweaking in Flash Builder. This is a bit of a hack, really.

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer