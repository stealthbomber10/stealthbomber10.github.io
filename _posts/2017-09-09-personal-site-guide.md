---
layout: post
title: "Trent's Dead-Simple Guide to Setting up a Personal Website as a Cheap College Student"
date: 2017-09-09 18:00:00 -0500
categories: guide
---
So you've decided you want to have your own personal website. You've seen the cool undergraduate students at your university showing off their portfolios and blogs and whatever with their fancy HTML pages, and you've made up your mind that you want whatever it is they're having.

Lucky for you, this is the golden age of web development (for better or worse), and you need literally zero knowledge of programming to set up a personal site. So you business school kids can follow along to!

You're also lucky to encounter an expert like me just doling out advice. In fact, I'm writing this post because it's what I wish had existed when I was making my site. All the info I used was pretty scattered amongst different resources on the Internet, and some of it was even out of date. I have yet to find a single article that combines all of what I learned, so I'm consolidating it here to speed up the process.

This guide will cover using GitHub Pages, Jekyll, Namecheap, and Cloudflare to make a secure, fast, good-looking website with little effort and no cost. Jekyll is the template for making a site, GitHub Pages is the service used to host it, Namecheap is for registering and configuring the domain, and Cloudflare is for (essentially) speeding up and securing the site. There's something to be said for putting in the time to craft your own page from scratch. On the other hand, you're a student, and you've got crap to do.

(Note: You can still follow this guide even if you're not a university student; it just won't be *completely* free bit because of the small cost for a domain.)

### Setting up GitHub Hosting

First things first, check if you have Ruby installed by opening up Terminal (or [Git Bash](https://git-scm.com/downloads) if you're on Windows) and running `ruby --version`. If it returns something like `ruby 2.X.X` you're good to go; otherwise go [here](https://www.ruby-lang.org/en/downloads/) and install the latest version of ruby.

While you're at it, if you don't have one already, go ahead and create a [GitHub](https://github.com/) account.

Create a [GitHub](https://github.com/) account login. [create a new public repository](https://help.github.com/articles/creating-a-new-repository/) and set the name of the repository to be `<username>.github.io`, where the username is your GitHub username (for example, the name of the repository for this site is `trentandraka.github.io`). Don't initialize a README or a `.gitignore` or anything else yet.

It should look something like this (except "user" is replaced with your actual username):
![My helpful screenshot]({{ site.url }}/assets/screenshot1.png)

Under your repository name, click `Settings`, and then under `GitHub Pages`, click `Choose a theme`. You can choose whatever theme you want, but I personally think the `Minimal` option is fine (it's the theme of this site after all).