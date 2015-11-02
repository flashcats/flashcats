---
title: 'Day 11: Flickr Feed'
author: bear
layout: post
permalink: /2011/03/30/day-11-flickr-feed/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Custom Skinnable Components
---
One more skinnable component I created a while ago while I was learning to write skinnable components. It pulls a list of recent images uploaded to Flickr, with the ability to search by tag or user id. The component uses a list skin part, meaning you will need to work with an existing skin in order to preserve the list skin part assignment.

Click on the image to view the swf.

[<img class="aligncenter size-full wp-image-564" title="FlickrFeed" src="http://flashcats.net/wp-content/uploads/2011/03/FlickrFeed.png" alt="" width="400" height="404" />][1]

I went with a refrigerator magnet theme. If you're lucky, you may be seeing another skin from Tara.

You can download the FXP [here][2].

Details after the jump.

<!--more-->FlickrFeed States

  * Loading: The component is loading the feed, and has not yet added the first image to the thumbnails list
  * Active: The component is displaying image thumbnails
  * Fault: An error has occurred while loading the flickr feed
  * Disabled: The component is disabled (this is uncommon)

Parts

  * Add Photo Delay Ms (RichText): Delay between adding new photos to the list, in milliseconds
  * Max List Size (Rich Text): Maximum number of thumbnails to display in the list
  * User Ids (Rich Text): Comma separated user ids used to filter the feed (optional)
  * User Tags (Rich Text): Comma separated user tags used to filter the feed (optional)

&nbsp;

 [1]: http://flashcats.net/static/skinnable-flickr-feed/FlickrFeedApplication.swf
 [2]: http://dl.dropbox.com/u/21428091/FlickrFeed.fxp