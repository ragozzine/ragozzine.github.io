---
title: "Rejecting Master for Main"
date: 2020-10-18
slug: "master-to-main"
draft: false
tags: ["tech"]
math: false
toc: false
---

Recently, I launched a new open source project. Unofficially called the [Last First Letter Collab](https://github.com/ragozzine/last-first-letter-collab), the story is built using a writing pattern: a sentence’s first word must begin with the previous sentence's last word's last letter.

While creating the repo on GitHub, I was pleasantly surprised to see that the default branch, heretofore always named `master`, was now called `main`.

We all know that words carry power. A person’s word choice can make or break a conversation, a motto, or even a simple salutation. Calling a group of people [“guys“](/posts/2016-03-16-ixnay-on-the-you-guys/) or narrowing down a tough choice by singsonging [“Eeny, meeny, miny, moe”](https://en.wikipedia.org/wiki/Eeny,_meeny,_miny,_moe#American_and_British_versions) can carry unintentional maliciousness. Seeing GitHub taking action with word choice, I decided to replace the default branch of this website’s repo from `master` to `main`.

Doing this is surprisingly straightforward. GitHub plans to [retroactively apply this naming convention to existing repos around the end of 2020](https://github.com/github/renaming), but I preferred not to wait. As the sole contributor to my humble Hugo blog, this update was 100% painless. I found a [solid tutorial](https://www.git-tower.com/learn/git/faq/git-rename-master-to-main/) on Git Tower (despite not using the product - sorry!) but to save you a click, here are the highlights:

1. Replace your local `master` with `main`

    ```git branch -m master main```

2. Rename your remote `master`

    ```git push -u origin main```

3. Delete the remote `master` (_You’ll probably need to reset the repo’s default branch on GitHub itself before remote deletion will be successful_)

    ```git push origin --delete master```

In the big picture — hell, even in the very very small picture — my changing `master` to `main` doesn’t matter, per se. It doesn’t change centuries of systemic racism. It cannot undo the innumerable (and completely avoidable) police shootings across the US. It’s barely a gesture, but it isn’t nothing.

Words carry power. Using terminology with racist origins or undertones isn’t ok. And to me, the normalized words and phrases — master, gypped, peanut gallery, selling someone down the river  — are worse because most people don’t know (and don’t care to know) where they came from.

> If you’re looking for a few podcasts on word origins, consider [this episode of _The Allusionist_](https://www.theallusionist.org/allusionist/ghostwriter), in which another podcast, [_Rough Translation_](https://www.npr.org/2019/04/30/718729150/we-dont-say-that), features.

There are so many small things we can do to erase little bits of prejudice from our world. So if I can move beyond the words with a few terminal commands, why wouldn’t I?
