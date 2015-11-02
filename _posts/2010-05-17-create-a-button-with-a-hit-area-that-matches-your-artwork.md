---
title: Create a Button with a Hit Area that Matches Your Artwork
author: bear
layout: post
permalink: /2010/05/17/create-a-button-with-a-hit-area-that-matches-your-artwork/
aktt_notify_twitter:
  - no
categories:
  - Wireframe Components
tags:
  - button
  - hit area
  - mouse events
  - transparency
---
<div id="_mcePaste">
  When you convert artwork to a button in Catalyst, by default your button responds to mouse input inside the artwork's rectangular bounds. This area that responds to mouse input events from the user (mouse click, hover, enter, exit, etc.) is called the hit area. If you have multiple buttons whose hit areas overlap, the topmost rectangle will always get the click event. Sometimes your button hit areas may overlap, or sometimes you may have oddly shaped buttons and the default hit area isn't quite right.
</div>

<div>
  <a href="http://flashcats.net/wp-content/uploads/2010/05/hitareadiagram.png" rel="lightbox[12]"><img class="aligncenter size-medium wp-image-14" title="Hit Area Diagram" src="http://flashcats.net/wp-content/uploads/2010/05/hitareadiagram-300x196.png" alt="" width="300" height="196" /></a>
</div>

<div>
  Here's how to make your button hit areas match your artwork exactly.
</div>

<div>
  <!--more-->
</div>

<div>
  <a href="http://flashcats.net/wp-content/uploads/2010/05/buttonexample.png" rel="lightbox[12]"><img class="aligncenter size-medium wp-image-13" title="Example Artwork" src="http://flashcats.net/wp-content/uploads/2010/05/buttonexample-300x196.png" alt="" width="300" height="196" /></a>
</div>

<div>
  <ol>
    <li>
      Select your artwork and convert it to a button (Right click -> Convert Artwork to Component -> Button)
    </li>
    <li>
      Double click the button to enter Edit In Place Mode
    </li>
    <li>
      Select all of the artwork in your button skin (Edit -> Select All)
    </li>
    <li>
      Convert the selection to a group (Modify -> Group)
    </li>
    <li>
      In the properties panel in the lower right, choose the Graphics header and deselect "Transparency accepts mouse"
    </li>
  </ol>
</div>

<a href="http://flashcats.net/wp-content/uploads/2010/05/propertiespanel.png" rel="lightbox[12]"><img class="aligncenter size-medium wp-image-16" title="Group Properties Panel" src="http://flashcats.net/wp-content/uploads/2010/05/propertiespanel-221x300.png" alt="" width="221" height="300" /></a>