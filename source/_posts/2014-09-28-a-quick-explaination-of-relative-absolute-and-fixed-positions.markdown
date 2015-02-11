---
layout: post
title: "A quick explaination of relative, absolute, and fixed positions"
date: 2014-9-28 12:55:47 -0800
comments: true
categories:
---
<p>This last week has been intense! I’ve basically gone from zero knowledge of HTML and CSS to creating this very website you are reading this on. But don’t be fooled! I put in a ton of work and had to battle though some major frustration to get here. So what was the hardest part for me to learn? By far it was understanding CSS positioning.</p>
<!-- more -->
<p>I still have a long ways to go before I’m an expert with positioning, but I’ve learned some important basics that I’m gonna share with you right now! So to get you started, let’s discuss the conceptual differences between relative, absolute, and fixed positions.</p>
<p class="bold">Relative Position</p>
<p>When an element's position is set to "relative" you can move it around <span class="italic">relative</span> to where it would normally be displayed. Let's say you have an image inside of your footer with a relative position. By default, this image should just show up inside your footer on the left side. Setting "right: 10px;" will place the image 10 pixels from the right side of your footer. So in other words, this image has moved <span class="italic">relative</span> to the footer. Pretty simple right?! Give it some practice and try for yourself!</p>
<p class="bold">Absolute Position</p>
<p>Think of an element with an "absolute" position as suck on the page like a sticker. It ignores any other elements and is placed on the page exactly where you tell to to be! If you place it 300px from the top and 40px from the left, it will always be 300px from the top and 40px from the left. The only thing it is positoned relative to is the entire web page itself.</p>
<p class="bold">Fixed Position</p>
<p>An element with a "fixed" position doesn't move for anyone! Other elements can't push it around and even scrolling will not move it. Fixed positioning is great for when you want a menu bar that always shows up no matter where you are on the page.</p>
<p>So there you have it! It's important to solidify these concepts before you start messing with positioning stuff on your website. Sorry it's so brief but it's late and I need some sleep! ;)</p>