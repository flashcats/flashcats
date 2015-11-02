---
title: How do I get components to reset after changing states?
author: bear
layout: post
permalink: /2010/06/15/statefulness/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Components
  - Interactions
  - Moderate
---
When you transition between pages or states in Catalyst, objects remain just as you left them. If you moved a scrollbar or slider in Page 1, then transition to another page, the scrollbar or slider will be in the same position as you left it. Often, you would like these components to reset, so that when you come back to them, they appear as if you had arrived at Page 1 for the first time.

We'll talk a bit about why Catalyst behaves the way it does, and how to achieve the desired effect after the jump.

<!--more-->

### The Explanation Bit

Which I find interesting, but if you're just looking for a how to you can skip it.

Catalyst behaves according to a *stateful model*, which is just fancy talk meaning that Catalyst keeps track of the *state* that you left components in. Think about it this way. Say you are ordering a book online. You fill out a web form (Page 1) with your shipping address and credit card information, then press next. At the next page (Page 2), you realize you made a mistake and go back to the previous page (Page 1) to fix it. If the form is blank, then the form is behaving according to a *stateless model*, meaning the form doesn't preserve information when moving amongst pages. If the form contains your previously entered information, then it is behaving according to a *stateful model*, because the form is remaining in whatever *state* you left it. The terminology is great, right, because we have yet **another** notion of state (which is, mind you, different than Catalyst component states; we'll be getting to those shortly).

### The Example

Here is an example of a custom component with several different "color" states, and a scroll panel. Notice how the different components behave if they are acting statefully or statelessly.

[kml_flashembed publishmethod="dynamic" fversion="10.0.0" movie="/static/statefulness/Main.swf" width="500" height="650" targetclass="flashmovie"]

[![Get Adobe Flash player][1]][2]

[/kml_flashembed]

### How it Works

Put simply, we add a couple extra actions to the transitions from Page 1 > Page 2, and Page 2 > Page 1 in order to reset them to their initial state.

To get the Custom Component to reset, we select the component and open the timeline. For the Page 1 > Page 2 transition, we choose Add Action > Set State > State 1 (the initial state of the component). Whenever we transition from Page 1 > Page 2, the custom component will go back to its initial state.

To get the Scroll Panel to reset is a bit more difficult, because we can only work with the Scroll Panel's enabled and disabled states. To make matters more complicated, because it's not a Custom Component, we can't set its state directly. But, setting the enabled property will indirectly set the Scroll Panel's state. Here's what you do:

  1. Open the Scroll Panel in edit in place
  2. In the Normal state, select the scroll bar
  3. In the Properties Panel's Component section, set the **value** property to 1
  4. Switch to the Disabled state. Set the **value** property to 2
  5. Exit edit in place. Select the Scroll Panel you want to have reset to its initial scroll position.
  6. In the appropriate transition (in this case Page 2 > Page 1), choose Add Action > Set Property > Enabled > False. The Enabled and False options are to the right in the Properties Panel after you add the Set Property action.
  7. Add another Set Property > Enabled > True action and drag it out to occur just after the initial set property action.

And there you have it. By setting the enabled property to false, then true, you toggle the Scroll Panel between the Normal and Disabled states. This will adjust the value of the scrollbar, which will set the position of the Scroll Panel's content. Tricky, eh?

### Some Notes

You need to explicitly set the Scroll Panel's Scroll Bar's value in each state to a different value. The values also need to be non-zero. If you leave the number as zero (the default value), the Scroll Bar will assume it can use the default value and won't explicitly set it. We need the values to be explicitly set in order for the Scroll Bar thumb's position to properly adjust. After you have set the two state's value property to different, non-zero numbers, you can go back and set one of them to be zero.

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer