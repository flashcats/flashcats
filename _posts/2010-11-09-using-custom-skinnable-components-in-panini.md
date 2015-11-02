---
title: Using Custom Skinnable Components in Panini
author: bear
layout: post
permalink: /2010/11/09/using-custom-skinnable-components-in-panini/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Custom Skinnable Components
  - Easy
tags:
  - Custom Skinnable Components
  - skinning
  - slide deck
---
I'd like to do a quick introduction to custom skinnable components in Panini. Panini, in case you haven't heard, is the code name for the next version of Flash Catalyst, and you can download a trial version on [Adobe Labs][1]. Custom skinnable components are a new feature in Panini, one that can make life for both designers and developers significantly easier. For this example, we're going to build the following swf.

[kml_flashembed publishmethod="dynamic" fversion="10.1.0" movie="/static/csc-slidedeck/Main.swf" width="400" height="300" targetclass="flashmovie"]

[![Get Adobe Flash player][2]][3]

[/kml_flashembed]

While this was possible in Catalyst 1.0, it could be a lot of work to add an additional "Slide" and the corresponding button interactions. With custom skinnable components, it's incredibly simple because a developer can create a component with the "Go forward" and "Go backward" logic built right in.

Is Panini sounding tasty? Take a bite!

<!--more-->

Disclaimer: This is written for a preview version of Flash Catalyst Panini, so features and terms may change as the product evolves.

First off, let's take a look at what exactly custom skinnable components are. In Flash Catalyst, the Button, Horizontal Scrollbar, and Data List are all components that are part of the Flex framework. The Flex team built these components to cover the most common interactive objects people need. But, sometimes you need something special for your project, either a component that's just a little bit different from a Flex one, or something new entirely. That's where custom skinnable components come in. Developers can create components with their own skin parts, skin states, and behaviors that can be brought into Flash Catalyst. Then, in Catalyst, you can give them a unique visual appearance the same way you would for a Button, Data List, or any other component in Catalyst CS5.

In this tutorial, I'm going to talk about using an existing custom skinnable component. At a later date, I'll go through the process of actually creating one in Flash Builder.

## The Walkthrough

To start with, you'll need to download the example project [here][4]. It's in a zip archive, so you should be able to unzip it to get an FXP you can open in Catalyst.

[I've updated the file, again >.< because there were still some problems with the old one]

If you open up the project, you should see a custom component displaying "Slide 1", a button displaying "Prev" and a button displaying "Next". You can see each of these in the layers panel.

<a href="http://flashcats.net/wp-content/uploads/2010/11/CSC-Overview.png" rel="lightbox[447]"><img class="aligncenter size-full wp-image-451" title="Custom Skinnable Component Overview" src="http://flashcats.net/wp-content/uploads/2010/11/CSC-Overview.png" alt="" width="400" height="272" /></a>Double click on the "Slide 1" area to take a peek inside the content custom component. You can see that there are three graphics or "Slides" that move around based on what state of the component you're in. Press "Esc" to jump back to the main art board.

Select everything (Cmd/Ctrl-A) and choose Convert Artwork to Component > Skinnable Component from the HUD.

<a href="http://flashcats.net/wp-content/uploads/2010/11/CSC-ConvertToCSC.png" rel="lightbox[447]"><img class="aligncenter size-full wp-image-453" title="Convert to Custom Skinnable Component" src="http://flashcats.net/wp-content/uploads/2010/11/CSC-ConvertToCSC.png" alt="" width="450" height="251" /></a>

A dialog will pop up listing all the custom skinnable components that are available in the current projects. Custom skinnable components can be bundled in an FXP, or imported into a project via an FXPL. In this case, the "Slide Deck" component was part of the starting FXP. Choose that and click ok.

Another dialog will pop up prompting you to name your component. Choose something reasonable and click ok.

<a href="http://flashcats.net/wp-content/uploads/2010/11/CSC-NamePicker.png" rel="lightbox[447]"><img class="aligncenter size-full wp-image-456" title="Name Picker" src="http://flashcats.net/wp-content/uploads/2010/11/CSC-NamePicker.png" alt="" width="322" height="154" /></a>

Let's take a quick break to talk about this Slide Deck component we have just created. Like a Scrollbar or Button, the Slide Deck has predefined states, parts, and behaviors.

  1. A Slide Deck has a single "Normal" state
  2. A Slide Deck has 3 parts. A "Content" custom component. Each state of the custom component represents a "Slide". You add or remove slides by adding or removing states from the content component. You specify Slide transitions by customizing the state transitions of the Content component. The Slide Deck also has "Previous" and "Next" buttons.
  3. Clicking on the Next button moves the Content custom component one state forward. Clicking the Previous button moves the Content custom component one state backward.

To make the new Slide Deck fully functional, we're going to need to do some part assignment. Double click on the Slide Deck, or choose "Edit Parts" from the HUD.

To assign the necessary parts, just select an item and choose Convert to Slide Deck Part from the HUD. To make this really easy, you can just select objects in the Layers panel and assign them. Select ContentComponent in the layers panel, and choose Convert to Slide Deck Part > Content Custom Component. Repeat these steps for the PrevButton and NextButton layers.

Try previewing your project (Cmd/Ctl-Enter). That's all there is to it!

Quick note: I used manual bounds on the ExampleSlideDeck and ContentComponent, both with clip to bounds set. You can check out this [previous post][5] for a longer example of using clip to component bounds.

## Long Winded Catalyst Musings

A "Custom Component" is a freeform item created in Catalyst, while a "Custom Skinnable Component" is a template item like a Button or Data List with defined visual states, behaviors, and properties. The major differences: You can modify the states in a Custom Component in Catalyst, while a Custom Skinnable Component has defined states and skin parts. The behavior on a custom skinnable component is built-in, while on a Custom Component you will have to define it yourself.

Behind the curtains, a skinnable component has two parts. It has the logic part, written by a developer, and the visual part, created by the designer. Technically logic part is the skinnable component (be it a Button, Scrollbar, or SlideDeck), and the visual part is the custom skinnable component *skin* (a Button Skin, a Scrollbar Skin, a SlideDeck Skin). Most of the time in Catalyst, we're working with skins, not actual components. This is the subject for an entire article about how the Flex underneath Catalyst works, but that's going to have to wait for another time. If you're ready to completely and totally geek out, you can check out the [Flex skinning documentation][6].

 [1]: http://labs.adobe.com/technologies/flashcatalyst_panini/
 [2]: http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif
 [3]: http://adobe.com/go/getflashplayer
 [4]: /static/csc-slidedeck/SlideDeck-no-ds-store.fxp.zip
 [5]: http://flashcats.net/2010/08/03/another-image-gallery-using-data-lists/
 [6]: http://help.adobe.com/en_US/flex/using/WS53116913-F952-4b21-831F-9DE85B647C8A.html