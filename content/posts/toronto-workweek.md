---
title: "Toronto Workweek"
date: 2018-08-06
draft: false
---

![Toronto's City Hall, Nathan Phillips square](https://www.macleans.ca/wp-content/uploads/2016/07/MAC31_TORONTO-ARCHITECTURE_POST01.jpg) _Awesome (work)week in Toronto without the lights, sights, Blue Jays, CN Tower or Timmies._


# Toronto Workweek

Until last week I had only heard of the term "workweek" mentioned on multiple occasions in my short time at [Mozilla](www.mozilla.org). Last week from very early Monday (4:30 am) to late Friday (11:45 pm) I had my work week in [Toronto](https://en.wikipedia.org/wiki/Toronto). Workweeks are an opportunity to do some work on a project, collaborate with fellow Mozillians, checkout the local office if there is one but also to an extent enjoy the location where you are during that week.

Toronto was great, the little of it that I saw. I stayed in a hotel that was very centrally located in the Entertainment district; stayed in a room with a view of the [CN Tower](https://en.wikipedia.org/wiki/CN_Tower) and the stadium next to it; it had great amenities and lots of food options nearby. This was great but nothing in my opinion compares to the results of a productive and successful workweek, one in which thanks to the invaluable help and guidance of my mentor there, allowed us to accomplish what we had set out to do.

We have a working extension! There's plenty of work to be done on it as the timeline on my project nears (Aug. 14th) and there's plenty of polishing and finishing touches needed but it works, it's functional and does what it is supposed to do.

## What's Involved

Prior to heading into Toronto there was a functionality to the project that I was happy with. Scanning was occurring, results were printing out and a confidence percentage was available. I knew that I'd need to get that functionality on-demand by right clicking into the image but how to do that? A brief but not unrelated aside: one of the many take aways that I will have from working on this extension is how amazing a resource [MDN](https://developer.mozilla.org/en-US/) is and how much I can depend on it, how many people use it and its ease of use.

[Context menu item](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/user_interface/Context_menu_items) is the feature to achieve on-demand right click functionality that provides a drop down menu to put the extension in use. This was great news to discover but using it meant needing to trach

## How It All Works

![Screenshot of image with text, right click drop down menu](https://raw.githubusercontent.com/hamletv/Images/master/Image%20A11y/Screen%20Shot%202018-08-01%20at%2010.54.34%20PM.png)
_Once the extension is installed, right click on the image you want to scan. The Image A11y icon and "Discover Image Text" option will show at the bottom of the context menu._

![Screenshot of image with text, inspector open showing image attributes](https://raw.githubusercontent.com/hamletv/Images/master/Image%20A11y/Screen%20Shot%202018-08-01%20at%2010.58.20%20PM.png)
_Prior to scanning and clicking "Discover Image Text" you can see the img alt attribute is empty. The attribute will be reassigned and scanned text will be injected there._

![Screenshot of image with text, inspector open, clicking on Image A11y icon](https://raw.githubusercontent.com/hamletv/Images/master/Image%20A11y/Screen%20Shot%202018-08-01%20at%2010.58.56%20PM.png)
_With inspector still open (which is not needed during regular use), alt attribute still empty, right click and "Discover Image Text"._

![Screenshot of image with text, inspector open, Image A11y clicked](https://raw.githubusercontent.com/hamletv/Images/master/Image%20A11y/Screen%20Shot%202018-08-01%20at%2011.00.36%20PM.png)
_Image has been scanned and the alt attribute now has text from image. Alt attribute text always starts with "Possible text:" due to the potential inaccuracies mentioned above._

## What's next?

Work is not finished. The extension, and it can be called an extension is 90% (+/-) complete. There are several Github issues that will need to be resolved but many of these will most certainly need beyond the summer to get reviewed and approved.
