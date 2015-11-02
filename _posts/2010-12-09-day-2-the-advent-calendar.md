---
title: 'Day 2: The Advent Calendar'
author: bear
layout: post
permalink: /2010/12/09/day-2-the-advent-calendar/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Uncategorized
---
It's time for the second custom skinnable component. It's an Advent Calendar! It even lets you cheat if you want to take a peek forward or backward in time <img src='http://localhost:8888/flashcats_wp/wp-includes/images/smilies/icon_wink.gif' alt=';)' class='wp-smiley' /> 

[kml_flashembed publishmethod="dynamic" fversion="10.1.0" movie="/static/advent-calendar/AdventCalendar.swf" width="400" height="400" targetclass="flashmovie"]

[![Get Adobe Flash player][1]][2]

[/kml_flashembed]

  * Here is the whole project as an [FXP][3], and
  * Here are the skinnable components only, as an [FXPL][4].

More on the component structure after the jump.

<!--more-->This custom component has 3 states,

  * 12 26 to 11 31, when we're not quite ready to countdown to Christmas
  * 12 1 to 12 24, which is the countdown proper
  * 12 25, a special state for Christmas proper

Skin parts wise, there are

  * 25 Calendar Days, a Group of Calendar Days. The skinnable components will change these from their "Off" state to their "On" state, one a day, starting from the topmost in the layers panel.
  * Prev, Next, and Reset Buttons, to help you cheat time

Happy holidays!

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer
 [3]: http://flashcats.net/static/advent-calendar/AdventCalendar.fxp.zip
 [4]: http://flashcats.net/static/advent-calendar/AdventCalendarLibrary.fxpl.zip