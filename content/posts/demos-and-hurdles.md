---
title: "Demos, hurdles and demo hurdles"
date: 2018-07-09
tags: ["extension", "Screenshots", "DOM"]
draft: false
---

## Demo

My script is running. Yes! Small victories regardless of project complexity are awesome. There's nothing that makes one (at least me) feel more victorious than spending an inordinate amount of time on something that you feel shouldn't have taken an inordinate amount of time and then finally overcoming the (temporary) hurdle. A won battle can momentarily feel like a conquered war. With the script now working and producing an actual result (and even a confidence percentage of the output printed), it was time to do a demo. To be clear, there's still plenty of work to be done to call this would-be extension "completed" but demos are a good way for everyone involved to make sure that you do get to the "completed" stage by showing your stuff and subjecting it to constructive criticism.  This would not be my first demo as someone producing code that would have an ultimate purpose, a Firefox extension, but it was my second...and the first didn't really count and this would be my first demo to more than one person so anxiety loomed large.

The demo was for the Screenshots service team of Firefox, my mentors and accessibility folks. The intention was to see how to start the accessibility conversation for that realm; what can be done, what is and isn't possible, brainstorming and possibly integrate Tesseract.js into the Screenshots service to improve accessibility within that environment. While my code was producing the output I needed and expected, there was still the issue of it not using local files, as it should have been. Getting the correct configuration of the Tesseract.js local files has been the hurdle that's taking an inordinate amount of time and in my mind shouldn't but there will a lessoned to be learned from this at some point, meanwhile, onwards. The demo went on using the CDN after rescheduling twice; I received some much needed words of wisdom/pep talk from my mentor, the possibilities and uses of Tesseract were understood by the Screenshots team, I fielded a couple of follow-up questions and briefly touched on the possibility of training tesseract to yield better results. All in all the demo went well.

This demo however, was just the beginning. There are at least 2 additional demos in the near future involving mentors, senior engineers in addition to managers. While these future demos will be with mostly familiar faces (my team --Firefox Test Engineering plus selected guests and the Accessibility team) I don't think my anxiety will be diminished. A more finalized (i.e. the working extension) is what is expected and what I expect of myself. This of course means getting those pesky local files to kick in and adding new features.

## What's new you ask?

There is new functionality that the extension will require. Originally the extension was meant to scan through all images within a webpage when the page loads. However, even as I excitedly worked to set up my loop that would cycle through all the collected images, I knew that once the script was working this would be a procedure that would be very time consuming. Not only time consuming but in many occurrences it would be totally unnecessary. Not all images contain text, why spend the time to scan these and have nothing as a result? Why create create paragraph tags as the end result of running the extension, that would be empty and pollute the DOM? Image_A11y would need to be more selective and as a result faster too.

Solution: have it scan selected images, on demand. I've always known that scanning all the images was not ideal or appropriate but I was not spending time on an alternate approach. I just wanted to get it working. My mentor Yura thought of making the extension on demand with right click functionality. This sounds good to me.

Additionally, there may be a way to have tesseract scan only the part(s) of the image that contains text. This, if doable would also mean significant time savings and an increase in the accuracy of the results. If tesseract doesn't have to scan the entire image, it is less likely that the results will have illegible text (noise) as a result of it attempting to scan areas of the image that don't contain text at all and interpreting those areas. This is potentially big deal in my mind but I will need to do some more research to make sure it is a possibility.

## What's next?

Well, I have a work week coming up on July 23rd at the Toronto Mozilla office with my mentor. Certain things will need to happen and have been completed this coming week so that I can be ready for that work week and not feel unprepared. Namely, the extension while it may be polished at that point, it will need to be working, with local files. With that in hand, I will need to make the most of that week with my mentor. As far as I'm concerned the work week should be to polish the extension, pair program, get as much feedback from my mentor and others and prepare to kick off the first weekday back home with my major demo.
