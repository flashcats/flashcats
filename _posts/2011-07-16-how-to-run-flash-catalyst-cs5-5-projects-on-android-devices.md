---
title: How to run Flash Catalyst CS5.5 projects on Android devices
author: tarajane
layout: post
permalink: /2011/07/16/how-to-run-flash-catalyst-cs5-5-projects-on-android-devices/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Advanced
  - Catalyst Hacks
---
While playing around with Flash Catalyst 5.5 and Flash Builder 4.5 I realized it's pretty easy to get your Flash Catalyst projects onto android devices.

This tutorial will walk you through importing your Flash Catalyst CS5.5 project into Flash Builder 4.5, show you how to convert it to a Flex Mobile project, and finally run your project on an Android device.

As a heads up, **I use this strictly as a prototyping/proof of concept method** (no release version/to market apps). Flash Catalyst CS5.5 does not create projects optimized for flex mobile.

Requirements:

  * Flash Catalyst 5.5
  * Flash Builder 4.5
  * Motorola Xoom (or other Android device running at least FP 10.2)

<!--more-->

1. Start out with your Flash Catalyst 5.5 project you'd like to run on a tablet device.  
I created a really simple, two state application for the purposes of demonstration:  
<a href="http://flashcats.net/wp-content/uploads/2011/07/fc_to_mobile_1.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/fc_to_mobile_1-300x187.png" alt="" title="fc_to_mobile_1" width="300" height="187" class="aligncenter size-medium wp-image-602" /></a>

2. Save your project.  
I saved my on my desktop, as fc\_to\_mobile.fxp

3. Open Flash Builder 4.5

4. Click File > Import Flash Builder Project  
<a href="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.08.33-PM.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.08.33-PM-150x150.png" alt="" title="Screen shot 2011-07-16 at 10.08.33 PM" width="150" height="150" class="aligncenter size-thumbnail wp-image-606" /></a>

5. An import dialog appears. Click the 'Browse...' button to the right of 'File:':  
<a href="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.11.26-PM.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.11.26-PM-150x150.png" alt="" title="Screen shot 2011-07-16 at 10.11.26 PM" width="150" height="150" class="aligncenter size-thumbnail wp-image-607" /></a>  
Navigate to your Flash Catalyst project file (.fxp) in your file system. Click open.

6. A second import options dialog appears. The default settings should look as below, then press the 'Finish' button:  
<a href="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.14.05-PM.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.14.05-PM-150x150.png" alt="" title="Screen shot 2011-07-16 at 10.14.05 PM" width="150" height="150" class="aligncenter size-thumbnail wp-image-608" /></a>

7. You'll now see a Flex project has been created in the "Package Explorer" panel in Flash Builder. It has the same name as your Flash Catalyst project file... in my case: FC\_to\_mobile.fxp.  
<a href="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.20.27-PM.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.20.27-PM-150x150.png" alt="" title="Screen shot 2011-07-16 at 10.20.27 PM" width="150" height="150" class="aligncenter size-thumbnail wp-image-609" /></a>  
We've officially imported our Flash Catalyst project into Flash Builder.

8. Lets convert our Flex project to a Flex Mobile project. In the File menu, click new Flex Mobile project:  
<a href="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.23.53-PM.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.23.53-PM-150x150.png" alt="" title="Screen shot 2011-07-16 at 10.23.53 PM" width="150" height="150" class="aligncenter size-thumbnail wp-image-612" /></a>

9. Give your mobile app a name. I picked 'MobileTestApp':  
<a href="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.25.14-PM.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.25.14-PM-150x150.png" alt="" title="Screen shot 2011-07-16 at 10.25.14 PM" width="150" height="150" class="aligncenter size-thumbnail wp-image-613" /></a>

10. Click 'Next'. Deselect 'ios' and 'blackberry', and pick 'blank' application. Make sure your settings look like these:  
<a href="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.26.44-PM.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.26.44-PM-150x150.png" alt="" title="Screen shot 2011-07-16 at 10.26.44 PM" width="150" height="150" class="aligncenter size-thumbnail wp-image-614" /></a>

11. Click 'Finish'. You have now created an empty Flex Mobile application. You'll see it in the 'Package Explorer' panel next to your imported Flash Catalyst app:  
<a href="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.28.51-PM.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.28.51-PM-150x150.png" alt="" title="Screen shot 2011-07-16 at 10.28.51 PM" width="150" height="150" class="aligncenter size-thumbnail wp-image-615" /></a>

12. Now we need to do a bunch of copy and pasting. Basically, you want to copy all of your Catalyst files (and maintain project structure) into your new Flex Mobile project. In the case of my project, I had to copy the 'components' folder from the FC\_to\_mobile project to 'MobileTestApp' (under the src folder), and then the 'main.css + PrivateData.mxml' files under the 'Default Package' folder. If you have an assets folder, you'll want to copy that over too:  
<a href="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.34.24-PM.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.34.24-PM-150x150.png" alt="" title="Screen shot 2011-07-16 at 10.34.24 PM" width="150" height="150" class="aligncenter size-thumbnail wp-image-617" /></a>

13. The last piece of copy+paste, is to open your 'Main.mxml' file in your Flash Catalyst project... and copy the contents. Then open your main Flex Mobile project application file (in my case, MobileTestApp.mxml), select all, and paste the contents of your Catalyst Main.mxml file:  
<a href="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.39.24-PM.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.39.24-PM-150x150.png" alt="" title="Screen shot 2011-07-16 at 10.39.24 PM" width="150" height="150" class="aligncenter size-thumbnail wp-image-618" /></a>

14. Press cmd-s to save your project, or select 'File>Save'. If you have any errors, they probably have to do with either (a) you didn't copy over all your catalyst project files (b) you didn't preserve project structure on copy paste... check to make sure everything is under the 'src ' folder, or (c) you have some global interactions in your project which use 'Main.xxx', in which case you should replace 'Main' with the name of your mobile project (in my case, MobileTestApp).

15. Now lets try running your app in the device simulator. Right click your Flex Mobile project and choose 'Run As > Mobile Application':  
<a href="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.45.30-PM.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.45.30-PM-150x150.png" alt="" title="Screen shot 2011-07-16 at 10.45.30 PM" width="150" height="150" class="aligncenter size-thumbnail wp-image-619" /></a>

16. The 'Run Mobile Project' settings dialog now appears. Select the 'On Desktop' radio and choose 'Motorola Xoom' as an example:  
<a href="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.46.40-PM.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-10.46.40-PM-150x150.png" alt="" title="Screen shot 2011-07-16 at 10.46.40 PM" width="150" height="150" class="aligncenter size-thumbnail wp-image-620" /></a>

17. Click 'Run'. Your Flash Catalyst app will now run in a window simulating the size and orientation of the Motorola Xoom. You can manipulate the orientation through the simulator 'Device' file menu.

18. Now lets run our application on an actual Android tablet. On your Android device, go to 'Settings' and then 'Applications'. You should see an option listed here called 'Development'. Click that. Turn on all options (USB Debugging, Stay Awake, Allow Mock Locations).

19. Connect your Android device to your machine via USB.

20. Right click your Flex Mobile project in Flash Builder, and choose the 'Run As' menu option, and choose' Run Configurations'. Instead of selecting the 'On Desktop' option, select 'On Device':  
<a href="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-11.08.44-PM.png" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/Screen-shot-2011-07-16-at-11.08.44-PM-150x150.png" alt="" title="Screen shot 2011-07-16 at 11.08.44 PM" width="150" height="150" class="aligncenter size-thumbnail wp-image-633" /></a>

21. Click Run. Wait a minute or so. Your Flex Mobile application will be copied on your android device, and then automatically opened. Any 'on click' interactions you set up in Catalyst will work as 'on touch' interactions on the tablet:  
<a href="http://flashcats.net/wp-content/uploads/2011/07/photo-1.jpg" rel="lightbox[601]"><img src="http://flashcats.net/wp-content/uploads/2011/07/photo-1-300x225.jpg" alt="" title="photo (1)" width="300" height="225" class="aligncenter size-medium wp-image-623" /></a>

Voila!

**Other items to note:**  
- You'll want to make your app resizable in Flash Catalyst so that your app resizes nicely when rotating from portrait to landscape mode.

-If you need to make changes to your application after viewing it on an android device, you can either modify the code in Flash Builder, or edit your original Flash Catalyst project. Unfortunately you'll have to repeat all of the above steps to get the updated app onto a tablet.

-Again, this is just a neat workaround to get your Catalyst apps onto an Android device. Catalyst doesn't directly support this workflow, and does not produce mobile-optimized code. 

-RollOver/RollOut won't work on Tablet. Use 'Click' events instead.

-If you have errors/can't run, see Step #14 above to make sure you've addressed the issues I've listed.