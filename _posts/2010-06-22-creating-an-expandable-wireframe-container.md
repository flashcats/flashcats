---
title: Creating an Expandable Wireframe Container
author: Matt Cannizzaro
layout: post
permalink: /2010/06/22/creating-an-expandable-wireframe-container/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Custom Components
  - Interactions
  - Moderate
tags:
  - Components
  - Interactions
  - library panel
  - states panel
  - wireframe
---
Flash Catalyst comes with some useful wireframe components, but eventually you'll want a component that it doesn't offer. When this happens, you can easily create the component you want, add some interactivity and animation, and reuse the component throughout your projects. Let's dive into the process! <!--more-->

In this example, I will create an expandable wireframe container.

  1. Start with a blank application. Draw a rectangle roughly the size your container should be when it is expanded.
  2. Convert the rectangle to a custom component using the HUD.
  3. Double click on the custom component to edit it.
  4. In the States panel at the top of the Flash Catalyst window, press the* Duplicate State* button.
  5. You can double click on a state name to edit it. Name your first state "closed" and the second state "open".
  6. Click on the closed state in the States panel to select it.
  7. Reduce the height of the rectangle on the artboard to the size that your container should have when it is collapsed.

Now our custom component has two states, open and closed. You can add some content to the open state, and you might also want to add some title text to both states. Feel free to be creative, but we do need a way for our component to switch back and forth between the two states when we run our application. To accomplish this, we'll create a button that toggles between the two states.

  1. Select the closed state in the States panel.
  2. Draw a triangle in one corner of the component. This will be our open and close button, so convert it to a button using the HUD.
  3. Make sure the button is in both states by right clicking on it and choosing *Share to State  > All States*.
  4. Select the open state in the States panel.
  5. Select the triangle button and rotate it 90 degrees using the transform tool (hold down Shift while rotating to make this easier).
  6. With the button still selected, press the *Add Interaction* button in the Interactions panel, in the middle left of the Flash Catalyst window.
  7. Set up an interaction that plays the transition to the closed state when in the open state each time the button is clicked. You'll need to select states in the bottom two comboboxes, but you can leave the others at their defaults.
  8. Press the *Add Interaction* button again, and set up an interaction like the previous one, except play transition to the open state when in the closed state.

Now run your application. If you click on the  open / close button,  the container should  expand and collapse.

The next step is optional, but it can help your container appear more polished. While the transitions between the open and closed states on the container are currently very abrupt, you can customize them and make them more gradual or stylized using the Timeline panel.

  1. Look at the Timeline panel at the bottom on the Flash Catalyst window. On the left hand side of the panel, there is a list of all the currently existing timelines. There should be two, one from the closed state to the open state, and one from the open state to the closed state.
  2. Select the transition from the closed state to the open state.
  3. Press the Smooth Transition button to get a reasonable default.
  4. Press the Preview Transition button to see how the new transition behaves (the Preview Transition button looks like a Play button near the top of the Timeline panel).
  5. Repeat steps 2 - 4 for the open to closed transition
  6. Run the application to see the transitions in action.

Feel free to further customize the transitions in the Timeline panel. You can easily adjust the duration of the transition by selecting the effects that Flash Catalyst generated and changing their properties, or you can add new effects.

Now that we have a working wireframe container, you might want to use it in several places in your project.

  1. Open the Library panel, which is docked in the upper left hand area of the Flash Catalyst window, along with the Layers panel.
  2. The component that you created in the previous steps should appear in the panel. Double click on it and give it a descriptive name.
  3. To reuse the component in a different place in your project, simply drag it out from the library panel.

[kml_flashembed publishmethod="static" fversion="8.0.0" movie="http://flashcats.net/wp-content/uploads/2010/06/ExpandableContainer.swf" width="400" height="300" targetclass="flashmovie"][![Get Adobe Flash player][1]][2]

[/kml_flashembed]

 [1]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [2]: http://adobe.com/go/getflashplayer