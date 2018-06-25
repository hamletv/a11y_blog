---
title: "Image A11y: background, tesseract.js and scope"
date: 2018-06-11
tags: ["accessibility", "tesseract.js", "ocr", "screen readers", "aria-describedby"]
draft: false
---

![Visually impaired person using a screen reader installed on laptop computer](https://www.google.com/url?sa=i&rct=j&q=&esrc=s&source=images&cd=&cad=rja&uact=8&ved=2ahUKEwixtLy23O_bAhXop1kKHdoICPcQjRx6BAgBEAU&url=http%3A%2F%2Fg3ict.org%2Fresource_center%2Fnewsletter%2Fnews%2Fp%2Fid_515&psig=AOvVaw3AkXqI71f9Utaze3WSshgp&ust=1530047262021790)

## Origins of Image A11y
Simply put, the object of the Image A11y project is to improve web accessibility by making the content (specifically text) within images accessible to [screen readers](https://en.wikipedia.org/wiki/Screen_reader). The idea of Image A11y came about during the December 2016 [Mozilla All Hands](https://wiki.mozilla.org/All_Hands/Austin) conference in Austin, TX. While giving a demo of an accessibility project I had worked on to the Mozilla accessibility team I was introduced to [Project Naptha](http://projectnaptha.com/). Project Naptha is a Chrome only extension that OCR (object character recognition) scans images and has the added functionality of allowing for editing the text, translate or completely [delete without overly distorting](https://en.wikipedia.org/wiki/Inpainting) the remaining image. It is a very cool extension, in my opinion. It does not however, make that content it scans available to screen readers, it is not an accessibility tool...and that's ok. The idea of porting this extension into Firefox was considered but creating a new extension inspired by Project Naptha was ultimately decided with the use of Tesseract.js

## Tesseract.js
[Tessaract.js](https://github.com/naptha/tesseract.js#tesseractjs) is a port of the [Tesseract OCR engine](https://github.com/tesseract-ocr/tesseract), software originally developed by Hewlett-Packard (propietary) in the mid 1980's but was then released as open source in 2005 after years of laying dormant with little changes. Shortly after its release into the wild Google took over development in 2006. Tesseract.js powers Project Naptha and it will power Image A11y; it works with HTML tags --local copy or [CDN](https://en.wikipedia.org/wiki/Content_delivery_network), webpack and Browserify via npm or Node.js (npm). Since Firefox does not support Node.js and I didn't go the webpack route, I started testing on simple HTML pages with the CDN. In 2006 as open source software, Tesseract OCR was considered one of the more accurate OCR engines available. Throughout my testing I came to realize how situational that accuracy really was or rather it wasn't. But that's ok, more on this in a later post.  

## Project Scope
Traditionally and exclusively images are made accessible solely by adding an [alt attribute](https://www.w3schools.com/tags/att_img_alt.asp) to the <img> tag in the [HTML](https://en.wikipedia.org/wiki/HTML), that contains a brief description of the image, should the image not be able to display or for our purposes, not be seen. However, even this small a11y addition is frequently omitted. It would be nice to have a tool to automatically add that all important attribute to images with an accurate description, maybe it's out there already, I don't know. Disabled users and the field of web accessibility could certainly use all the help they can to improve content access. Image A11y will ultimately be a Firefox JavaScript based extension that will ideally improve access, even if it's just a little.

### High level overview/steps needed to make this happen:

  • When a page is loaded the script will collect all images within the page by accessing the DOM. Ideally it would only collect images with text in them to speed up the process --scanning can be relatively lengthy (seconds) depending on the image and number of images to scan through-- but I don't have/know of a way to distinguish between these images and to keep things simple this is the route I'll take for now.

  • With the images collected and in an array, set a function that will loop through each image and feed that image into Tesseract for scanning. I've noticed the speed of scanning is dependent on a number of variables such as size of text, font used, space between letters and words, quality of the text within the image, background applied to text and possibly others. Tesseract scanning results are not perfect and these variables definitely affect results but even minor (a11y) improvement is improvement and iteration is our friend. Additionally, training of tesseract is possible but more on that hopefully in a later post.

  • Once scanned, immediately after rather than printing to the console I'll have the function create a <p> tag linked to that image to add that scanned text into. Remember that this text is for screen readers! The look of the site itself will not (should not) be altered at all, sighted users will not notice anything different if the extension is running. Rather this newly created <p> tag containing the scanned text will be invisible but it will alter the DOM, where the screen reader will do its work.

  • Tag invisibility will be provided by [aria-describedby](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-describedby_attribute) attribute but I would also like to test altering the style of the <p> tag by just not assigning a font-size to the tag or setting it to 0 px, that should also make it invisible.

Ultimately the goal is to build an extension that can be easily added and will hopefully improve accessibility of website images to screen reader users without a noticeable lag in information/content being passed to the screen reader.

## Next steps

Next steps are making sure I can make tesseract.js run locally over simple HTML pages I create and then over any random page online. Once that's happened I can move the script into creating the extension. More details in the next post.
