---
layout: post
title: "Trent's Dead-Simple Guide to Setting up a Personal Website as a Cheap College Student"
date: 2017-09-09 18:00:00 -0500
categories: guide
---
So you've decided you want to have your own personal website huh? You've been looking at all the cool undergraduate students at your university showing off their portfolios and blogs and whatever with their fancy HTML pages, and you've made up your mind that you want whatever it is they're having.

Lucky for you, you are coming of age during the golden age of web development (for better or worse), and you literally don't have to know anything other than how to type and check off a few boxes. So you business school kids can follow along to!

You're also lucky to encounter a programming expert like me just doling out advice. In fact, I'm writing this post because I wish there had been something like it when I was making my site. All the info I used was pretty scattered amongst different resources on the Internet, and some of it was even out of date. I'm consolidating what I learned to speed up the process.

This guide will cover using GitHub Pages, Jekyll, Namecheap, and Cloudflare to make a secure, fast, good-looking website with little effort and no cost. Sure, there's something to be said for putting in the time to craft your own page from scratch and continously tinker with it. On the other hand, you're a student, and you've got crap to do.

(Note: You can still follow this guide even if you're not a university student; it just won't be *completely* free bit because of the small cost for a domain.)

### Setting up GitHub Hosting

First things first, check if you have Ruby installed by opening up Terminal (or [Git Bash](https://git-scm.com/downloads) if you're on Windows) and running `ruby --version`. If it returns something like `ruby 2.X.X` you're good to go; otherwise go [here](https://www.ruby-lang.org/en/downloads/) and install the latest version of ruby.

While you're at it, if you don't have one already, go ahead and create a [GitHub](https://github.com/) accounnt.

Login to your new account and [create a new repository](https://help.github.com/articles/creating-a-new-repository/), making sure to initialize it with a README. Also make sure to click `Add .gitignore` and select `Jekyll` in the scrolldown.  