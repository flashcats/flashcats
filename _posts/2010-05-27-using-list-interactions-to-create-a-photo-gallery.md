---
title: Using List Interactions to Create a Photo Gallery
author: Matt Cannizzaro
layout: post
permalink: /2010/05/27/using-list-interactions-to-create-a-photo-gallery/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Interactions
  - Moderate
---
Lists are great for displaying a series of items, but they also have some handy interactivity features. One such feature allows setting up custom interactions that run when a specific list item is selected.

<!--more-->

Start with a list containing some pictures, though you can use text too. For my example, the list will contain thumbnails, and clicking on a picture in the list will display a full size image along with a short title.

Suppose you're setting up a list view, and you'd like some item details to appear when an item is selected. Here's how to do it:

  1. For each item in your list, create a new page.
  2. Make sure the list is all in the pages: right click on it and choose *Share to State > All States*.
  3. Set up each page so it contains the content you'd like to show for corresponding list item. The first item in the list will be selected in Page1, the second item in Page2, and so on. Add any details you like to each state.
  4. Select the list, and create a new interaction for it by pressing the *Add Interaction* button in the Interactions panel, which is on the middle left side of the Flash Catalyst window, right above the Properties panel.
  5. In the interaction dialog, select the Page1 state from the *Choose State* dropdown.
  6. Select *When a specific item is selected*, choose Item 0, which should be the default, and press OK.
  7. Repeat steps 5 and 6 for each item in your list, associating Page2 with Item 1, Page3 with Item 2, and so on.
  8. Run your project and click on each list item to verify that your interactions are working.

Here's an example:

[kml_flashembed publishmethod="static" fversion="10.0.0" movie="http://flashcats.net/wp-content/uploads/2010/05/Main3.swf" width="800" height="600" targetclass="flashmovie"][![Get Adobe Flash player][1]][2]

[/kml_flashembed]

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer