---
layout: post
title:  "Dithering in Photoshop"
date:   2017-04-14 21:35:00 +0200
categories: jekyll update
---
I recently release a set of [Dither Brushes][dither-brushes] for Photoshop CS5 (and probably higher). It is [frowned upon][frowned-upon-tools] in the pixel art community to use tools when making pixel art, since at its core this community finds a challenge in placing every pixel seperately and purposely. They make perfect drawing within a grid and often with a limited color set. So why did I make this set publicly available, and what are my [recommendations](#recommendations) for using it? 
To answer this I will answer the following first:
* [What is Dithering?](#what-is-dithering)
* [How does dithering in the tool work?](#how-does-dithering-in-the-tool-work)
* [What kind of problems will I encounter with this tool?](#what-kind-of-problems-will-i-encounter-with-this-tool)

# What is Dithering?
Dithering is a technique used to make gradients in pixel art. While it is possible to use a wider range of colors, in pixel art is is often chosen to use a limited set. It uses a pattern of alternating colors to "mix" two (but rarely more than two) colors together. There are different patterns that can be used, each with a different "density" and style. 

Often two similar colors are used to create a color that is in between, but sometimes a grey is used to desaturate a color or red and yellow are mixed to make an orange. First color A than a mix of A and B until only color B remains. Such gradients can be very large, often it is only and area of a few pixels. This technique is widely used in shading art, but in more limited color sets (for older hardware) entire art pieces can consist of dithered areas.

>Example Image of dithering gradient  
>Example Image of dithering character

Nowadays the main reason for using it is for aestatic reasons. A nice talk on this kind of graphics, including dithering, is by [Mark Ferrari][mark-ferrari], who worked on a lot of 80's classics like The Secret of Monkey Island. And no, he doesn't understand why there are still people that want to make pixel art. But he does acknowledge the fact that such limitations make you very creative.

# How does dithering in the tool work?
So now that we have a little insight in what Dither is lets talk about how the tool works.

First I made 8 different 4 by 4 pixel patterns, of 2 colored pixels each, making it a pattern of `2/(4*4)=0.125` density. Each of the patterns was designed exactly to make it possible to combine them to make more dense patterns out of it. I named these patterns O, and A through G.

>Image of all OABDCDEFG patterns and how they combine.

I used these patterns as textures applied to Photoshop Brushes using multiply mode.

Took some thinking time, but it was pretty easy. Even making a touch sensitve version of the brush was simply using different greys to set the right threshold.

# What kind of problems will I encounter with this tool?
First of all the pattern found for 0.250 density is not perfect, although it is a widely used pattern, it does "reveal the grid" (has a very recognizable pattern). Therefor I introduced two seperate patterns that can be used instead. However each of these patterns do not line up either vertically or horizontally, placing two pixels of the same color directly next to eachother, breaking the smoothness of the gradient.
>Image of the two alternative brushes

It should also be noted that there is only one pattern, while the pattern an be shifted both up and down 3 more times effectively leaving 15 patterns behind that can not be used in the current set. These patterns can be recreated using the O, A... G brushes in a different order.

# Recommendations
Experiment! That's the best way of knowing what you can do with these brushes. But I will give you some general advice.

* Don't use the brushes right away, only use them if you need to dither large areas.
* Decide which color will be drawn as background and which color you will use in your foreground and keep to that for your entire object. If you don't you will come in situations where you are drawing the same color as both background and background, which removes the dither effect.
* If your object's grid doesn't line up with an object behind it consider moving the pattern you drew a few pixels, or use several of the primitive 2-pixel brushes to fix it. This will take some work, but make sure your object doesn't blend together with whatever is behind it.
* Zoom out often to see if you are not doing something that takes a lot of time to fix.

To help you out I disabled spacing, to force users to use the brush in a calm fashion, in hopes force people to use it more presicely.

Even with all the downsides that follow from what is considered "good" pixel art, I still think this brush can be really helpful. I personally like them, and I feel that when you keep the limitations in mind it will help you make good pixel art quicker.

In the end you should always retouch your dithers with a nice 1 pixel pencil to make everything look perfect. That is, if you are not a a Game Jam schedule.


{% include card-itchio.html id=133494 %}  

[dither-brushes]: https://abductedPlatypus.itch.io/dither-brushes
[frowned-upon-tools]: http://pixeljoint.com/forum/forum_posts.asp?TID=11299&PID=139318#139318
[mark-ferrari]:https://www.youtube.com/watch?v=aMcJ1Jvtef0