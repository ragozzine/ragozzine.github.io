---
title: "Creating an Ideal Epic"
date: 2017-10-30
slug: "jira-epic"
draft: false
tags: ["pm", "tech"]
math: false
toc: false
---

What I like most about managing projects with Jira is the level of organization and filtering I can achieve by tagging tickets. As someone who used to keep his CD collection in alphabetical order by artist (with secondary ordering done by year), the tagging options help me structure projects in a deeply satisfying way&mdash;except for labels, which totally bite (mostly).

![](/images/labels-bite.gif)

While not everyone uses components or fix versions (though you SHOULD) just about everyone who manages projects in Jira ought to make use of epics. And more over, everyone ought to use epics optimally. I know without a doubt that when I first started using Jira, I leveraged epics embarrassingly poorly. But I don’t blame my past self (or anyone) for “misusing” epics in Jira. Have you ever read [Atlassian’s definition of an epic](https://confluence.atlassian.com/agile/glossary/epic)?

> An epic captures a large body of work. It is essentially a large user story that can be broken down into a number of smaller stories.

Saying an epic is a large user story is akin to people explaining sprints as “little waterfalls.” I get how those explanations are arrived at—comparison is one of the easiest ways to grasp new concepts—but not moving beyond these distorting definitions can greatly hobble a Jira project.

## Agile at an Agency
My use of agile is within a web agency, My product owners are (typically) my clients, and many do not have substantive experience with scrum practices. What’s more, the product owner and the client are often one and the same. While good product owners keep stakeholder expectation inline with reality, clients (or humans as a whole) have tough times saying no, or not right now, to themselves.

Here’s where effective use of epics can pay serious dividends. Rather viewing an epic like a supersized user story, I think of epics as all the things the client wants at the end of the project, laid out like a grocery list. While you won’t have all the epics you will need to get to done at the beginning of the engagement, the bulk of the epics can be plucked right from the SOW deliverables. These come in handy during backlog refinements, since it paints a clearer idea for the client the steps necessary to complete a request fully. And once you have a slew of tickets, being able to visually show the breakdown of what work is needed to complete which deliverable is hugely beneficial. We may refine backlogs at the ticket level, but stepping back to assess at the epic level can put priorities in perspective.

## Not so epic epics
When I first started using epics, I would create groupings that made sense to me, but not so much to my clients. I still wince when I think back to epics like *CPTs* or *TinyMCE*. Using jargon that works for the dev team but not the client is 100% backwards.

Another mistake I made was having epics that were too large or ambiguous. I would make epics like *Templates* for front-end markup, or *Platform* for things related to the admin, database, or hosting environment. Again, this was me drawing lines of demarcation that would help me sort tasks, but to my clients the distinctions were irrelevant at best, confounding at worst.

Instead, when I am fleshing out a new website project in Jira, I add epics for all the stuff the client already knows they want. *Homepage* and *Forms* tend to make it into all of my project epic lists. From there, I create epics around any deliverable clearly laid out by the client that isn’t too broad. While *Responsive design* isn’t epic material, any cool feature (new or refreshed) described in the SOW will definitely be an epic.

The above are all the whizzbang epics within a project. But, without foundational work, a website would just be a seldom visited killer homepage surrounded by search engine trafficked inner pages that act like ugly cul-de-sacs. I always have an epic called *Global elements* as a catchall for things like the site header, navigation, and footer. It isn’t helpful to have a Header epic and a Footer epic, because there’s no point in prioritizing these against one another. Both are needed, so can share an epic and rely on story summaries to separate the work.

Anyone who is working with a CMS also needs an epic called Standard pages or something similar. The benefit of a CMS is the use of a single, cohesive templating theme across the majority of the site’s pages&mdash;for more than just blog posts. A large percentage of any site’s pages are basically the same template, so highlight this fact with a nice, shiny epic.

Often with CMS templates, a template is created that offers myriad options for layouts and other unique elements. This utility template helps site owners make visually and functionally distinct pages on their site with little to no technical know-how. There are lots of ways to name this epic, but some of my favorites are *Premium page*, *Über page*, and *Super page*. These names let the client know that this page does a lot, so might be worth prioritizing highly.

## More than a name
While I do love naming my epics, I really get mileage out of them by adding clear summaries to the epic ticket, detailing what it is meant to accomplish. Yes, calling an epic the *Awesomeness page* might be fun, but without intelligible acceptance criteria documented within Jira, something will get missed. Or, something will be assumed as included that can throw a wrench in the gears down the road.

Epic descriptions are easily reviewed and understood when added in list form. I tend to have these tickets reviewed and approved by every member of the project team during kickoff or sprint 0, so any misaligned expectations are remedied very early on.

## The 1-2-3s of epics
When all’s said and done, epics are most useful when they are:

* Based on a single project deliverable;
* Readily understood by all team members, regardless of their technical or business prowess, and;
* Given documentation inside Jira that the team all reviews and agrees upon.

All that being said, no project has all its epics on day one. It’s the nature (and benefit) of agile to allow the space for a project to evolve into the best solution that time, money, and scope will allow. To work best within project constraints, use epics to your (and your team’s) advantage.
