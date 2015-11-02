---
title: Making a Catalyst Swf Scalable
author: bear
layout: post
permalink: /2010/06/08/making-a-catalyst-swf-scalable/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Advanced
  - Builder Tweaks
tags:
  - builder
  - scale
  - scale mode
  - stage
  - swf
---
As you've probably figured out, the swf files Catalyst generates are a fixed size. Even if you set the size of the swf manually when you embed it, the content you created in Catalyst will remain the same size. But, with a little tweaking in Builder, you can make your swf scale to fit the width and height you set for it.

Look! It's the same swf at three different sizes!

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/swf-scale/Main.swf" width="50" height="50" targetclass="flashmovie"]

[![Get Adobe Flash player][1]][2]

[/kml_flashembed]

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/swf-scale/Main.swf" width="75" height="75" targetclass="flashmovie"]

[![Get Adobe Flash player][1]][2]

[/kml_flashembed]

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/swf-scale/Main.swf" width="100" height="100" targetclass="flashmovie"]

[![Get Adobe Flash player][1]][2]

[/kml_flashembed]

<!--more-->Here's what you'll need:

  1. Flash Catalyst and Flash Builder
  2. A Flash Catalyst Project you'd like to scale

Here's what to do:

  1. Save your project out and import it into Builder (In Builder: File > Import FXP). Choose your FXP under Import Project > File > Browse. The default settings should be fine for your import.
  2. Open up Main.mxml. You can find it in the package explorer (left panel) under *project name* > src > (default package) > Main.mxml.
  3. You should see the MXML markup used to create your application. We are going to modify the top level <Application> tag.
  4. Remove the width and height attributes on the Application tag.
  5. Add the following attribute: preinitialize="systemManager.stage.scaleMode='showAll'"
  6. Choose Project > Export Release Build to publish a version of your swf. By default, this goes in the "bin-release" folder in your Builder project.
  7. When you embed the swf in a web page, set its dimensions to make it scale.

That's all there is to it. There are some alternative scale modes, such as *exact fit*, which does not maintain the aspect ratio *show all* does. You can read up on those in the [ActionScript Documentation on StageScaleMode][3].

[Update] This is an older article for Catalyst CS5. I would highly suggest checking out resizability in the new "Panini" version of Catalyst available over on Adobe Labs.

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer
 [3]: http://www.adobe.com/livedocs/flash/9.0/ActionScriptLangRefV3/flash/display/StageScaleMode.html