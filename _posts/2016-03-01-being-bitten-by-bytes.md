---
title: "Being Bitten by Bytes"
date: 2016-03-01
slug: "bitten-by-bytes"
draft: false
tags: ["tech"]
excerpt_separator: <!--more-->
---

Collective nouns are single words for a group of things and I love them all (except for “guys”&mdash;that’s a bad one). I especially enjoy animal group names. Get three or more bears together, and it’s known as a sleuth. Same with a pride of lions, a bale of turtles, or a romp of otters. [Bird collectives have the best names](http://birding.about.com/od/birdingglossary/a/groupsofbirds.htm): a murder of crows, a chain of bobolinks, a deceit of lapwings.

Group terminology goes further than animals. A collective of houses could be a town. Words group together to form sentences. And a website is nothing more that a collective of files. A pile of files.

In this file pile, some items relate to simple things like font size or color choices. Others control complex things like data tracking and form handling. But surprisingly, more often than not, the largest files in the pile are the ones that do the least: images.

<!--more-->

Yup, images. A file that doesn’t really DO anything beyond sitting there looking pretty carries the most heft.

![](http://41.media.tumblr.com/tumblr_lscoscp0uk1r11y1eo1_500.jpg)

When someone visits your site, their browser needs to download every file in your file pile to finish. Typically, this is done linearly by rendering the [DOM](https://en.wikipedia.org/wiki/Document_Object_Model) from the first file up top all the way down to the file caboose. Meaning that, if you have a large file towards the top of your site DOM, that will have to download (more or less) before the next file is attempted, similarly to when you have a lot of downloading files on your laptop or app updates on your phone; there is only so much processing power to download things simultaneously.

If you have an especially large file (like a big, fat image) your visitor’s browsers will need to chug on downloading that before it renders other things, like content, ads, or even some styling.

Part of the strategy to handle this is to organize your DOM into a logical order. For example, you may employ some JavaScript to allow for infinite scrolling (re: when a reader scrolls to the end of the article/post, a new one pops up automagically). If you put this at the top of your DOM, it would block everything else, which is silly since you don’t need it right when the page is loaded. So, a smart web developer will put non-critical JS such as this in a site’s footer—at the bottom of the DOM.

But, we can’t put image files at the end of the DOM; they are often part of the page content and flow and need to be loaded further up the DOM. While there are lots of ways to handle this, a good way to start is to test your site and see what’s taking the most effort to download.

By way of examples, I used [WebPageTest.org](http://www.webpagetest.org/) to analyze the following websites to see how other sites handle this issue (if at all). I could have used [Pingdom’s Full Page Test](http://tools.pingdom.com/fpt/) or [Google Developers PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/), but WPT provides pretty pie charts with their results, and pie charts rule the day!

## Initial Results

### NYTimes.com
The <a href="http://www.webpagetest.org/breakdown.php?test=160228_7V_D8G">results for NYTimes.com</a> showed 39.6% of the file weight for their homepage being images, which isn’t too bad. But, I am going to lump in their custom fonts. I’m making some assumptions here, but the font files must be things like SVG sprites, so I’m going to include them (they are not typical web fonts so take more to download). I am also willfully IGNORING THE FLASH FILES THEY LOAD because ignoring Flash is the only sensible stance to take; odds are those are ads anyway.

![](/assets/images/speedtest-nyt.jpg)

**Final Tally: 51.5%** of all files loaded are image files, which is a bit more than half.

### Whitehouse.gov
Because I am a good American, I [tested WhiteHouse.gov](http://www.webpagetest.org/breakdown.php?test=160228_55_D7F) next. Once you include more pesky SVG fonts, we see that image files make up nearly 3/4 of the total homepage file size, which is pretty staggering. Talk about Washington DC bloat eh? Eh? Moving on...

![](/assets/images/speedtest-whitehouse.jpg)

**Final Tally: 69.5+%** of the White House’s homepage goes to loading image files.

### Twitter
Having focused on a publisher and a government site worried more about security than performance, I shifted gears and [tested Twitter](http://www.webpagetest.org/breakdown.php?test=160228_GF_D75). Not logged in and snappy Twitter, but the “Look at all we have to say—come join us” marketing masonry presented to non-logged in visitors. Most of the tweets displayed had images associated, which explains this page’s image heft weighing in at a little over half.

![](/assets/images/speedtest-twitter.jpg)

**Final Tally: 55.7%** of the files downloaded to display Twitter’s homepage are images.

### Wikipedia.org
Stymied by my results thus far, I decided to [test Wikipedia’s plain ol’ no-language-set homepage](http://www.webpagetest.org/breakdown.php?test=160228_49_D5Q), which has nearly no images on it. And despite that fact, it actually came in a little HIGHER than Twitter.

![](/assets/images/speedtest-wiki.jpg)

**Final Tally: 56.5%** of files fetched to build Wikipedia’s homepage are images.

### CodePen.io
I really wanted to find a site with a good balance of files, so I thought, “What’s a site that is made BY web-savvy folks FOR web-savvy folks?” Naturally, I [thought of Codepen](http://www.webpagetest.org/breakdown.php?test=160228_FD_DAR) and found something very interesting in its results. Its homepage’s image weight only clocked in at 25.2%, but the fonts requires to display the page came in at a crushing 31.4% (which to me, proves my SVG sprite hypothesis from the NYT site).

![](/assets/images/speedtest-codepen.jpg)

**Final Tally: 56.6%** of the file weight sprouts from sprites and images.

### A List Apart
Now, to be fair, Codepen is doing a LOT with their site, so I obviously give them a pass. What about the website that supports so much forward-thinking publishing for the front-end web world: A List Apart. I figured it would be about the same as The New York Times homepage, maybe even lighter given the limited homepage scope. But <a href="http://www.webpagetest.org/breakdown.php?test=160228_J3_D9H">my tests actually came in higher</a>. How much higher?

![](/assets/images/speedtest-ala.jpg)

**Final Tally: 59.1%** image-file weight for A List Apart’s homepage, potentially higher if we knew what the _Other_ wedge denoted.

### Drupal.org / WordPress.org
Perhaps the open source community would fare better? I ran speed tests for both [Drupal.org](http://www.webpagetest.org/breakdown.php?test=160228_VC_D74) and [WordPress.org](http://www.webpagetest.org/breakdown.php?test=160228_KM_D70). In both cases, what I found surprised me.

![](/assets/images/speedtest-drupal.jpg)

![](/assets/images/speedtest-wp.jpg)

**Final Tally: 69.5% of the files Drupal.org** says you need for their homepage are images, while **49+% of WordPress.org** homepage is made up of image bytes.

### Flickr
Clearly images are important to all these sites; they’re typically dedicating more than half a browser’s efforts to displaying them. What about a site that is all about images? I [tested Flickr](http://www.webpagetest.org/breakdown.php?test=160228_VE_VTF) and it did not disappoint.

![](/assets/images/speedtest-flickr.jpg)

**Final Tally: 88.4%** of Flickr’s homepage is made up of sweet, sweet images.

### WebPageTest.org (WPT)
_Quis custodiet ipsos custodes?_ / Who watches the watchmen?

Putting the shoe on the other foot, my [final test was on WebPageTest.org](http://www.webpagetest.org/breakdown.php?test=160228_J4_D8S) itself! Despite the only images being branding and their giant Partners sprite at the bottom of the homepage, the results show that even the watchmen need to go on a diet.

![](/assets/images/speedtest-wpt.jpg)

**Final Tally: 34.2%** of what loads every time to want to test a site is images.

## Solutions: Upfront and After-the-fact
There are tactics you can employ to put your image file-loading bulk on a diet. Some are done right upfront, while others work for repeat visitors. It’s worth noting that a true web engineer likely has a zillion other suggestions, but here are just a few.

**Upfront solutions:**

* One solution is to simply **be stingy with your use of images**. Eye candy might be ocularly delicious, but be aware of the hurdles images might place between your readers and your content; be critical, especially of images that aren’t part of the content. Design window-dressing might be hurting your UX inadvertently. One helpful tip is to [develop a performance budget](http://danielmall.com/articles/how-to-make-a-performance-budget/) as a way of identifying a benchmarked ceiling for your live site.
* Before uploading to your site, **save your images optimally**. Choose reasonably small dimensions and save at the smallest file size possible. #photoshopsave4web4eva If you’ve ever been on a subpar site and had to sit and wait while a thumbnail slowly loads, you are seeing the consequences of not doing that. The 100px square thumbnail was uploaded at 2000px square, forcing the browser to download a huge file that will be displayed teeny tiny. Don’t do that.
* Image files are more than what you see. Compressed images on your site won’t weigh you down too badly.

**Live Site Solutions:**

* As I said earlier, some of the dangers of large image files has to do with blocking the DOM; the browser spends time downloading files it doesn’t need yet. A different way of combatting this with images is to **employ lazy loading**. The strategy is to delay downloading the images until the reader needs them (re: once they scroll to the image part of the page content). Think of it as rendering procrastination. If you’re using WordPress, there are many plugins that do this, such as [Lazy Load](https://wordpress.org/plugins/lazy-load/).
* If your site doesn’t have caching, get that going ASAP. My very non-technical assumption on how **page caching** works is, with caching, visitors aren’t downloading all your site files with every page load. Instead, some of those files are saved in the visitor’s browser, so they don’t have to download them again. This makes pages load faster, which is a big plus. It’s like, imagine if every time you wanted to see a beautiful painting, you had to hang the heavy frame on the wall. What an inefficient pain. Let the good stuff stay on the wall all the time with caching.
* Image load-times benefit when sites **use a CDN**. [I’ve written about CDNs before](/posts/2015-12-06-a-cdn-simple-visual-explanation/), but to sum up, it again has to do with downloading files. You see, despite how wondrous our world is, every website file is still stored on a physical server someplace. And, it takes longer to download files the further they are stored from you. “Longer” in this instance may only mean thousandths of a second, but every little bit counts. Use a CDN like CloudFlare or JetPack and get your image files closer to the people who want to load them.

So which solution(s) should you employ? To help you focus your efforts, look to WPT’s scoring matrix combined with the second scan they do for every test. Remember, some of the solutions are only workable AFTER a visitor has loaded your site more than once, so the repeat scan results can sometimes be more valuable than the initial ones.

So how did a few select sites do when given a second chance?

Whitehouse.gov and WordPress.org both did much better. While Wikipedia broke even and WPT did worse.

![](/assets/images/speedtest-whitehouse_REPEAT.jpg)

![](/assets/images/speedtest-wp_REPEAT.jpg)

![](/assets/images/speedtest-wiki_REPEAT.jpg)

![](/assets/images/speedtest-wpt_REPEAT.jpg)

Let’s review some scoring to figure out why.

### Whitehouse.gov
![](/assets/images/speedtest-whitehouse_SCORE.jpg)

Despite not compressing their images, the Whitehouse folks did a good job with page caching and an excellent job with using a CDN. Nearly no images had to be re-downloaded during their second pass.

### Wikipedia
![](/assets/images/speedtest-wiki_SCORE.jpg)

Wikipedia scored poorly for caching, and was awarded an “N/A” for compressing of images. The latter means WPT couldn’t “find” any images on the site, which still doesn’t make sense to me. Wikipedia does NOT use a CDN (effectively), so got dinged here as well. That’s why all the images downloaded for the first scan had to be re-downloaded for the second. No es bueno.

### WPT
![](/assets/images/speedtest-wpt_SCORE.jpg)

Despite great scores for many categories, WPT scored “worse” for image file percentages (74.8%) for their second scan. I use quotes because it might be math screwing with us. My guess is that the caching combined with the CDN altered the file ratio, making images stick out like a sore, fat thumb. Remember, if all you download is a single file, that’s 100% of what you downloaded. Damn you, math!

To sum up, images aren’t bad things, despite sometimes being worthless eye candy. However, just like with real-life candy, you have to be smart and moderate your intake. Use optimized images in targeted ways and mix in smart caching and a CDN; you don’t need to sacrifice page speed for design elements.
