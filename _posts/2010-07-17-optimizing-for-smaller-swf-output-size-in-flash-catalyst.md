---
title: Optimizing for smaller swf output size in Flash Catalyst
author: tarajane
layout: post
permalink: /2010/07/17/optimizing-for-smaller-swf-output-size-in-flash-catalyst/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Library Assets
  - Quick Tips
tags:
  - embedded images
  - image compression
  - linked images
  - loading time
  - optimize artwork
  - swf filesize
---
To decrease site loading time, your goal as a web devsigner is to get the smallest swf size possible.

Large SWF files typically contain lots of full resolution artwork, embedded content(image, video and audio files) and complex paths.

Luckily, Catalyst provides you with some options for optimizing your project.

In this post, I'll discuss a few of the most common. If used appropriately, you'll see loading time decreasing, and happier customers/clients who'll stick around past the default flex preloader to see your awesome rich content. 

<!--more-->

### **1) Creating linked images**

By default, all images imported into Catalyst are embedded.

**What does this mean?**  
They are compiled (and hence included) into the swf file.  
If you import a 5mb background image into Catalyst, your swf just got 5mb bigger.  
This means each time a user/customer navigates to your site, it has to load that 5mb image right off the bat.

**What is a linked image?**  
A linked image is an image located externally with respect to your swf.  
Your image file isn't compiled (included) into your final swf file, but sits outside your swf.  
It's \*not\* included in the final swf size.  
Since your image file will sit outside the swf file, you will need to be sure to copy it to your webserver.  
Linked images are loaded on the fly, so they might take a second to load the first time.

**How do I create a linked image in Catalyst?**  
1) Navigate to the library panel  
2) Look for an image file in your project  
3) Right click on the image file in the library panel  
4) Choose 'Convert to linked image...' from the context menu  
5) Click OK if an explanatory dialog pops up

<a href="http://flashcats.net/wp-content/uploads/2010/07/optimization_linkedImage.png" rel="lightbox[224]"><img src="http://flashcats.net/wp-content/uploads/2010/07/optimization_linkedImage-300x219.png" alt="" title="optimization_linkedImage" width="300" height="219" class="aligncenter size-medium wp-image-322" /></a>

**How do I distinguish between linked and embedded images in the source code?**  
Embedded images:

<div class="wp_syntax">
  <div class="code">
    <pre class="mxml" style="font-family:monospace;"><span style="color: #000000;"><span style="color: #7400FF;">&lt;s:BitmapImage</span> source=<span style="color: #ff0000;">"@Embed('logo.png')"</span><span style="color: #7400FF;">/&gt;</span></span></pre>
  </div>
</div>

Linked Images:

<div class="wp_syntax">
  <div class="code">
    <pre class="mxml" style="font-family:monospace;"><span style="color: #000000;"><span style="color: #7400FF;">&lt;mx:Image</span> source=<span style="color: #ff0000;">"logo.png"</span><span style="color: #7400FF;">/&gt;</span></span></pre>
  </div>
</div>

**How do I distinguish between linked and embedded images by looking at my published project?**  
1) Open the run-local or deploy-to-web folders in your published project directory (either works)  
2) Double click the assets folder name.  
- Assets (images, videos, audio) which are external are located in this directory.  
- Assets which are embedded are \*not\* located in this directory.

**  
**

### **2) Optimized Vector Graphics**

** **

**The skinny:**  
- Converts a bunch of vector art into a single low level flash *Graphics* object, moving the selected vector art into its own FXG(more on FXG to come... we'll cover it soon!) file.  
- It renders quicker as opposed to having 500 paths being rendered one by one. You'll notice a performance difference in Catalyst, and in your final swf.

**Why optimize vector graphics?**  
1) Performance in Catalyst. If you're dealing with a lot of vector artwork, Catalyst will be rendering each vector individually. Why not combine the ones which you can into an optimized version? Now Catalyst only has to render \*one\* graphics object for you instead of those 20 rectangles.

**What's the advantage in optimizing vector graphics vs rasterizing?**  
Simply put, you can always break apart optimize graphics.  
So if there's a vector within your optimized graphic that you suddenly have a dying urge to animate, or convert to component... you can just break it apart and you are back where you started.

**So, how do I optimize vector graphics?**  
1) Select all the artwork you'd like to optimize either directly on the artboard by using the selection tool, or in the layers panel.  
2) In the floating HUD, choose 'Optimize Artwork', and then 'Optimize Vector Graphics'.  
<a href="http://flashcats.net/wp-content/uploads/2010/07/optimization_optimizeVectorGraphics.png" rel="lightbox[224]"><img src="http://flashcats.net/wp-content/uploads/2010/07/optimization_optimizeVectorGraphics.png" alt="" title="optimization_optimizeVectorGraphics" width="261" height="215" class="aligncenter size-full wp-image-329" /></a>

### **3) Rasterize**

**The skinny?**  
-Use it to convert a bunch of complicated paths to a bitmap image. (to learn more about rasterizing, check wikipedia)  
-Notice a performance difference in both Catalyst and your project at runtime.

**Rasterize vs optimized graphics**  
1) When you rasterize, you don't have the option to break apart (like you do with optimized graphics). Unless you undo the operation, your rasterized graphic is here to stay.  
2) Additionally, rasterized graphics don't scale nicely. Use optimized graphics when you want to maintain scalability.  
3) Unless your rasterize graphic takes up the entire screen, it is generally more performant than an optimized graphic.

**So, how do I rasterize images?**  
1) Select all the artwork you'd like to optimize either directly on the artboard by using the selection tool, or in the layers panel.  
2) In the floating HUD, choose 'Optimize Artwork', and then 'Rasterize'.

<a href="http://flashcats.net/wp-content/uploads/2010/07/optimization_rasterize.png" rel="lightbox[224]"><img src="http://flashcats.net/wp-content/uploads/2010/07/optimization_rasterize.png" alt="" title="optimization_rasterize" width="260" height="214" class="aligncenter size-full wp-image-333" /></a>

### **4) Compress Image**

Catalyst does not complete any image compression by default when you import a large image.

**What is an uncompressed image?**  
An image at initial filesize and quality. It's the default condition of an image you pull from your DSLR card without doing any editing, for example.

**What is a compressed image?**  
An image in which redundant pixels have been eliminate to reduce quality (to a percentage) and in turn reduce filesize.

** Why compress images in Flash Catalyst?**  
We're creating content for the web here! The smaller our final swf size, the better the initial load time. We don't want to lose the attention of customers/clients during our initial site loading.

**How do I compress images in Flash Catalyst?**  
1) Right click on an image in the library panel.  
2) You'll see the 'compress image...' option listed... click it.  
3) Select your compression options. The smaller the percentage you choose, the smaller your filesize (and lower quality).  
4) Click OK.  
5) Your image which was previously on the artboard, will be replaced with a compressed version of itself.

<a href="http://flashcats.net/wp-content/uploads/2010/07/optimization_compression.png" rel="lightbox[224]"><img src="http://flashcats.net/wp-content/uploads/2010/07/optimization_compression-300x261.png" alt="" title="optimization_compression" width="300" height="261" class="aligncenter size-medium wp-image-336" /></a>

Other tips for optimizing artwork, or good reads on the subject:  
1) [Adobe Flash Catalyst Help - Optimizing Artwork][1]  
2) [Design was here: Design battle vector vs raster][2]  
3) [In Obscura: Optimizing images for web][3]

 [1]: http://help.adobe.com/en_US/flashcatalyst/cs/using/WSe0363cf428f0b465ffa9edb1273635cfd7-8000.html
 [2]: http://designwashere.com/design-battle-vector-vs-raster/
 [3]: http://inobscuro.com/tutorials/read/35/