---
title: "QA Will Give Me a Bug-free Website and Other Lies We Tell Ourselves"
date: 2016-01-21
slug: "qa-lies"
draft: false
tags: ["qa"]
math: false
toc: false
---

If you work for a large corporation or on a project with limitless coffers, you have likely enjoyed working with a dedicated QA team. You build the website or oversee the coding efforts then hand off your labors to a separate team who systematically kicks the tires and identifies bugs with your work, reporting back on everything.

But, for the bulk of web work, QA and testing is not done by a standalone team with that single purpose. Rather, it’s one of many hats worn by everyone on a build team. Whether you’re a developer or a designer or a PM, everyone has a role in the QA process.

So what’s a PM’s role in QA? Well, besides testing finished work BEFORE the client gets access to it, a project manager’s primary role in QA is to set the proper expectations. This expectation-setting is twofold:

* Clearly articulate to the client what a feature will and will not do.
* Explain realistically to the client that QA will not catch every single bug.

## What a feature will and won’t do
Firstly, what’s a code bug? It’s when code does not work. It is NOT when code does not work as expected. As such, project managers or whomever is handling client communications needs to absolutely nail down what the code will and will not accomplish.

I do not mean this as a defense of rigid, immutable requirements documents; a feature can shift over time and should not fall prey to an uninformed, early scoping effort. However, a client should not be left with ambiguous feature descriptions. Likewise, a direct review of what the outcome will be in the end needs to happen and be agreed upon by all involved. Make sure that clients know exactly how their (possible) non-technical request will be delivered technically and walk through functionality in layman language. For you WordPress folks, remember that no one knows what the hell a CPT is outside of (and sometimes within) the Community.

Just because I pull into a gas pump on the wrong side of the car does NOT mean my car was built incorrectly. I either [had the wrong expectations as to where to access the gas cap](https://www.youtube.com/watch?v=bwog7Z858iE), or I am not driving the car that I am used to, so acted on misplaced habits. The same is true when expectations either are not or are inadequately set with clients. When they don’t see what they assumed they would, they will flag it as a bug. But this isn’t a coding issue&mdash;it’s a project management issue and as such, needs to be handled as part of any project communication workflow.

![](/images/PpopHm.jpg)
Most cars nowadays have a little arrow to help you remember which side of the car the tank access is located. Still, I literally double-check this each time I pull up to a gas station. I do this out of fear of embarrassment because OF COURSE EVERYONE PAYS ATTENTION TO ME WHEN I PUMP GAS. #automobilemicrocopy"

## QA won’t find every issue
Secondly, while the aspiration is to squash all of them, even the most robust QA process will not catch every single bug. This is not an issue with the testing methods themselves or a sign of a weak development team. The reality is that QA will never find every bug before you go live. Anyone who tells you differently is flat out lying to you.

Now, a solid QA process will greatly mitigate production bugs, but about 10% of them will make it through anyway. That means that, as a PM or client manager, you have to approach this head-on with your client stakeholders.

It only takes a single bug within a project for it to be labeled “buggy”, so do what you can to minimize malfunctioning code from making it to the live site. Here are a few quick tips to limit bugs on production sites.

### Favor many smaller deployments over the “one big push” method
While it is very tempting&mdash;not to mention dramatically satisfying—to do a big reveal of a website, the smarter way forward is to consistently push small chunks of finished code to production the entire time. There is a solid correlation between delayed code deployments and the likelihood of coding bugs and conflicts arising. The more time between code being “finished” and the same code being shipped, the more issues you will have post-deployment.

### Test the front-end and the back-end
So often with site work, when it comes to QA, people focus exclusively on the front-end of the site. How does this look in a few browsers at a few window sizes and **BOOM** testing done! Not only is this inadequate for the front-end, but no one bothers to check the back-end and how it functions. This is crucial as, often, post-launch bug reports are really “how the heck does this work?” inquiries. Be deliberate in what you test.

### In fact, test the whole site
Obviously there are matters of scale to consider here, but code isn’t as siloed as some would have you believe. One change to a site’s infrastructure can have unexpected ripples across the codebase, so be aware of what files are changing and test other dependent functions as appropriate. This includes both code in your staging environments as well as legacy code already in production.

### Keep it real
This rule transcends a few points, but the takeaway should be to use real users, real browsers, real situations, and real content. Obviously your team will be the first to test things, but be sure to mix up disciplines as you can (i.e. have a front-ender test a back-end admin implementation) . A fresh perspective always helps any testing process. And no QA process is complete without a client weighing in, so be sure to communicate that directly and, before they dive in, go over your code with a fine-toothed comb.

Also, when you can, have tests done in true, native browsers. Yes, tools like [BrowserStack](https://www.browserstack.com/) can do a great job in certain scenarios. But when you can, ferret out someone who actually HAS a browser installed natively to do some testing. This is the truest test and can often bring unexpected, browser-specific quirks to light.

The biggest issue with QA is when you don’t use real data and content. Testing a layout with “Test Article” copied over and over again as the headline won’t set you up for success once you launch and the layout becomes dependent on article titles that are four lines long. Writing is as rhythmic as music; we all tend to use a detectable pattern in our word and sentence lengths, so avoid doing QA with Lorem Ipsum or other filler text. [Design from the content out](http://wordpress.tv/2015/09/30/john-eckman-design-from-the-content-out/), and only test when you have real words and images fueling your layouts.

In conclusion, remember that it’s impossible to ship bug-free code, but you can definitely do what you can to ensure that what you do deploy is high-quality code of which you can proudly call your own.
