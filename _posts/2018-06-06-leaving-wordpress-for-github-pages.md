---
title: "Leaving WordPress for GitHub Pages"
date: 2018-06-06
slug: "wp-to-github-pages"
draft: false
tags: ["tech", "wordpress"]
excerpt_separator: <!--more-->
---

I’ve been a [WordPress user since 2007](/posts/2015-10-26-the-aux-of-wp-rethinking-the-wordpress-writing-experience), continuously maintaining personal writing sites. I grew along with the product, moving from a casual hobbyist suffering through the Famous 5-minute Install to a WordPress professional, making my living from the open source CMS.

And while WordPress is a solid foundation for many web projects, a blog isn’t one of them anymore. Often derided as being “just for blogs,” WordPress’s product roadmap has steadily veered further and further from a platform for low-volume sequential writing with each jazzy release. While it’s empowering for a non-technical writer to wield plugins to tweak their WordPress blog in any way they see fit, be they janky or no, plugins rarely fully satisfy out-of-the-box. WordPress could only be the writing tool for me because I knew what chaff to deactivate, uninstall, or otherwise work around to get a post published.

<!--more-->

With the slapdash future that is [Gutenberg](https://wordpress.org/gutenberg/) in core, I started to seriously question maintaining a WordPress site for my web publishing endeavors. Plus, I missed the small technical hurdles of old WordPress, digging around in PHPMyAdmin to remedy some side effect I introduced to the codebase by installing a <em>must-have</em> social share button plugin. Was it worth the (admittedly small) annual cost for web hosting to prop up a shoddy McMansion when a 3-bedroom ranch would suffice?

I started searching around for no cost, no frills alternatives to blogging with WordPress and quickly Googled my way to [GitHub Pages](https://pages.github.com/). With a little technical knowhow&mdash;or comfortability with following online tutorials&mdash;I could have a blog with no out-of-pocket costs (unless I chose to add a custom domain which, at the time of this writing, I have not done). Frankly, with the ebb and flow of my article publishing, it didn’t make sense to me to spend *any* money to have a website up and running.

## Moving from WordPress to GitHub Pages
While I could manually hardcode every piece of my publishing process, I chose the static site generator Jekyll to provide templates for my soon-to-be site. There are oodles of online tutorials for setting up a GitHub Pages blog using [Jekyll](https://jekyllrb.com/), so I’m not going to detail all my steps here. Rather, I do have a few broad pieces of advice.

> *Note: Since this original posting, I have swapped out Jekyll for [Hexo](https://hexo.io/) then [Hugo](https://gohugo.io/) then [Gatsby](https://www.gatsbyjs.com/) then [Svelte](https://kit.svelte.dev/) and now (Jan 2023) back to GitHub Pages. Why? I am trying to keep it simple and keep forgetting to do that when something shiny comes along.*

If you embark on migrating your WordPress blog to GitHub Pages, know that you will make a lot of false starts. Rather than starting with the site content migration, take the time to get comfortable generating a Jekyll-powered GitHub Pages site using the command line. You don’t <em>have</em> to use the command line but it’s kinda cool and not as scary as you may think.

I created a GH Pages site again and again, testing out this tutorial and that Jekyll theme again and again and again until I was fully satisfied with what I created.

From there, I had to get all of my content out of WordPress in a Jekyll-ready fashion. I wound up using the [Jekyll Exporter](https://wordpress.org/plugins/jekyll-exporter/) plugin, which extracted all of my posts, pages, and media in no time. The only snag I found was in how image tags were structured inside articles; the URL path was incorrect. A find-and-replace in my IDE took care of this hurdle rather painlessly.

So now I have a no-cost online presence that scratches my writer itch as well as my web dev inclinations. For me, it’s the best of both worlds.
