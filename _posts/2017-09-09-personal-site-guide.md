---
layout: post
title: "Trent's Dead-Simple Guide to Setting up a Personal Website as a Cheap College Student"
date: 2017-09-09 18:00:00 -0500
categories: guide
---
So you've decided you want to have your own personal website. You've seen the cool undergraduate students at your university showing off their portfolios and blogs and whatever with their fancy HTML pages, and you want whatever it is they're having.

Lucky for you, this is the golden age of web development (for better or worse), and you need literally zero knowledge of programming to set up a personal site. So you business school kids can follow along to!

You're also lucky to encounter an expert like me just doling out advice. In fact, I'm writing this post because it's what I wish had existed when I was making my site. All the info I used was pretty scattered amongst different resources on the Internet, and some of it was even out of date. I couldn't find a single article that combines all of what I learned, so I'm consolidating it here to speed up the process.

This guide will cover using GitHub Pages, Jekyll, Namecheap, and Cloudflare to make a secure, fast, good-looking website with little effort and no cost. Jekyll is the template for making our site, GitHub Pages is the service used to host it, Namecheap is for registering and configuring the domain, and Cloudflare is for (essentially) speeding up and securing the site.

Now, there's still something to be said for putting in the time to craft your own page from scratch. On the other hand, you're a university student, and you've got crap to do.

(Note: You can still follow this guide even if you're not a student; it just won't be *completely* free bit because of the small cost for a domain.)

### Setting up GitHub Hosting

First things first, check if you have Ruby installed by opening up Terminal (or [Git Bash](https://git-scm.com/downloads) if you're on Windows) and running `ruby --version`. If it returns something like `ruby 2.X.X` you're good to go; otherwise go [here](https://www.ruby-lang.org/en/downloads/) and install the latest version of ruby. Ruby is the programming language that will run our site.

While you're at it, go ahead and initialize the site:

```shell
$ gem install bundler jekyll
$ jekyll new mysite
```
You can replace `mysite` with whatever you want the name of the folder to be. This installs the stuff needed to build the site and then creates the site.

Create a [GitHub](https://github.com/) account login. [Create a new public repository](https://help.github.com/articles/creating-a-new-repository/) and set the name of the repository to be `<username>.github.io`, where the username is your GitHub username (for example, the name of the repository for this site is `trentandraka.github.io`). Don't initialize a README or a `.gitignore` or anything else yet.

It should look something like this (except "user" is replaced with your actual username):
![My helpful screenshot]({{ site.url }}/assets/screenshot1.png)

Now go back to your terminal and run the following commands:

```shell
$ cd mysite
$ jekyll serve
```

This will automatically start running your site. You should be able to access it at [http://127.0.0.1:4000](http://127.0.0.1:4000). Visit that URL in your web browser, and you should see this:
![My helpful example]({{ site.url }}/assets/example.png)

Now quit your terminal session and start up another one. Run the following commands:

```shell
$ cd mysite
$ git init
$ git add --all
$ git commit -m 'Initial commit'
```

Now you just need to sync this folder with your repository on GitHub. Run the follwing commands in the still-running session (replacing `username` with your GitHub username):

```shell
$ git remote add origin git@github.com:username/username.github.io.git
$ git push -u origin master
```

You'll have to enter your GitHub username and password (yes, the characters don't show up when you type, that confused me too when was first learning the command line). Now, if you go back to your GitHub account, you should see all the files for your site in your online repository for the site. If you go the URL of your site, which should be <username>.github.io you'll see what you saw earlier when you were running the site ony our computer. GitHub hosts your site for free on its servers.

But the URL can only be `something.github.io`. What if you want one of those fancy schmancy custom domains?

### Registering a Domain

It's a good thing [Namecheap](https://www.namecheap.com/) has a cost-effective solution. Go and [register](https://nc.me/) the free domain you get just for being a university student. You'll also have to make an account. The free option is the one with the `.me` subdomain (that's what the domain ends with, for you business students). Even if you don't like the `.me`, it's worth the price. You get a year of free domain hosting, and even after the year is up the price to renew is small. Plus, with your own website, you'll be set with cash from that big internship you'll no doubt score.

After Namecheap walks you through registering the domain, you'll eventually arrive at your Dashboard. For reference, here's mine.
![My dashboard]({{ site.url }}/assets/namecheap.png)

Now don't close that tab, as we'll be coming back to it later.

### Setting up Cloudflare

We're getting into Uber 1337 h4x0r territory here, since most university students don't know how to do this and thus don't bother to learn. [Cloudflare](https://www.cloudflare.com/) was the subject of an embarrassing data leak earlier this year, but it's still a pretty useful service. Most importantly for us, it's free (at least in our use case).

Make an account on their [website](https://www.cloudflare.com/) and register your whatever.me domain with their service (it'll walk you through the steps, and it's free). When it asks you to verify your DNS records, just hit continue. Make sure you select the free plan.

![DNS crap]({{ site.url }}/assets/dns.png)

You should eventually be presented with a page like so. These are the nameservers you'll add to your Namecheap account so that we can use Cloudflare's services with the site:
![My helpful nameservers]({{ site.url }}/assets/nameserver.png)

Now go back to your Namecheap dashboard and click on `Manage` right next to your domain. Right next to where it says `Nameservers` in the list under the `Domain` tab, select `Custom DNS` in the dropdown. Add the nameservers that Cloudflare presented you with to route your domain through cloudflare. For reference, here is the setup for this site:
![My custom stuff]({{ site.url }}/assets/custom.png)

Now if you go back to Cloudflare and click `Recheck Nameservers` under Overview, it should eventually give you a green light with a Status that says `Active` (though it might take some time).

Now we flip some magic switches that'll speed up our website and make it more secure. Go back to your Cloudflare account and navigate to the `Crypto` page under your domain. Set SSL to `Flexible`. Set both `Always use HTTPS` and `Automatic HTTPS Rewrites` to `On`. Next go to the `Speed` tab and check off `Javascript`, `CSS`, and `HTML` next to `Auto Minify`. Finally, go to `Page Rules`. You get three free page rules, so enable the following rules: (1) `Always Use HTTPS` for your http domain (like http://trentandraka.me, (2) `Forwarding URL` for the `www` version of your domain (like from https://www.trentandraka.me to https://trentandraka.me) with `Permanent Redirect` enabled, and (3) `Cache Level` for your domain (like https://trentandraka.me/) with `Cache Everything`. For reference, these are the page rules for this site:
![My rule1]({{ site.url }}/assets/rule1.png)
![My rule2]({{ site.url }}/assets/rule2.png)
![My rule3]({{ site.url }}/assets/rule3.png)
![My rules]({{ site.url }}/assets/rules.png)

So what did all that do? Essentially, it enabled a bunch of settings that use the power of Cloudflare's servers to speed up the site and make it more secure. The secure part comes from using `HTTPS` instead of `HTTP`. It's always good for a site to have the former over the latter, since it's safer for users and gives the site a higher page-rank in search engines. The changes won't take effect immediately, however; you might have to wait a bit.

Disclaimer: the site still shouldn't be used for handling sensitive data, as the free Cloudflare services don't provide full end-to-end encryption, and Github [explicitly says](https://help.github.com/articles/what-is-github-pages/) "GitHub Pages sites shouldn't be used for sensitive transactions like sending passwords or credit numbers." For our purposes, however, this level of security is perfectly fine, so get over it Snowden. Most students just keep the custom domain completely unsecured with plain `HTTP`.

### Final Steps

The moment of triumph (with a little bit of configuration). Go back to the repository for your site on GitHub and click `Settings` at the top. Scroll down until you see `GitHub Pages`. Enter your domain in the Custom Domain box and hit Save. Refresh the page and you should see something like this:
![My cname]({{ site.url }}/assets/cname.png)

Your site is finally viewable at https://yourname.me.

Now edit the template so that it looks like a human operates the site. Go back to the main page of your repository and click on `_config.yml`. This is all the variables that show up on the main page of the site. Edit these accordingly by clicking on the pencil icon in the top-right (for reference, mine is linked [here](https://github.com/trentandraka/trentandraka.github.io/blob/master/_config.yml)).

Edit the `about.md` file in your repository too with a dandy description of who you are (or whatever it is you're representing).

And that's it. You now have a super fast personal website that even provides security for it's users. How much did it cost? Nothing. How much programming did we do? Also nothing.

If you want to try your hand at customizing the site even more, check out the [Jekyll Docs](https://jekyllrb.com/docs/home/).

If anything went wrong with your site during this tutorial, try [installing gentoo](https://www.youtube.com/watch?v=VjGSMUep6_4).