---
layout: post
title: "Choosing Your First Programming Language"
date: 2017-09-10 1:00:00 -0500
categories: essay
---
For some reason, several people I know seem to take me as some sort of computational prodigy solely because I'm the only one they talk to who has any sort of programming experience. The question I get most often from these people is why I don't have a girlfriend.

...

Another question I get a lot is what language is best for getting into programming. It's a legitimate question that I remember googling when I first started out, and people give a wide variety of answers to this query. Part of that is just because people naturally have different opinions on the strengths of different languages, but what's also true is that the answer depends on the goals of the person asking.

I've developed my own personal take on the issue. Now whenever people ask me what language they should start with, I can just point them to this post.

### The Gist: Learn Python or Lisp

No, Java is not the answer. A trash language being used by every employer and university in the country is still a trash language. Don't punish newcomers for Java being popular at one point.

As pointed out in Part 3 of [this post](https://gavinfreud.github.io/programming/2017/09/04/the-significance-of-hello-world.html), Python's emphasis on simplicity and readability make it so that even a non-programmer can intuitively understand it's syntax. It's dynamically typed and does all memory allocation for you, too, so you don't even have to worry about weird type conversion or segfault errors. The weaknesses of Python (slow runtimes, single-threading) don't even affect a beginner programmer either.

Python is also a powerful language that is used prominently in a variety of disciplines, e.g. data science, web development, and database management. So if someone doesn't know why they want to learn programming or what they want do with such a skill, Python covers a lot of bases. Plus there are a billion libraries available for it, so for a lot of stuff you can let other people do the work for you.

There's a just as good, if not better, alternative, however.

Lisp isn't commonly brought up for, well, anything anymore, but there's a reason it's the favorite languange of rockstar programmers like [Richard Stallman](https://stallman.org/stallman-computing.html) and [Paul Graham](http://www.paulgraham.com/avg.html). In fact, take it from Stallman himself:

>The most powerful programming language is Lisp. If you don't know Lisp (or its variant, Scheme), you don't know what it means for a programming language to be powerful and elegant. Once you learn Lisp, you will see what is lacking in most other languages.

And yes, he has seen Python. He still thinks Lisp is better. Lisp is also the language used by the most famous [computer science book](https://mitpress.mit.edu/sicp/full-text/book/book.html) ever, so it's really got a lot of street cred in computer science.

I haven't used Lisp as much so I can't speak that well about it, but from the little I've read I can say that it requires a fundamentally different way of programming. It eschews focusing on syntax and instead centers on thinking more mathematically. For years MIT used it as it's language of choice for their introductory programming class because students didn't have to bother memorizing syntax like they would for, say, Java. Lisp has fewer learning resources and libraries, but lots of people rave about that book I linked above, so maybe try that. 

So yeah, go with either Python or Lisp and you'll be fine.

### Hard Mode: Learn C

Stallman, however, has another favorite programming language: C. Yes, there's a difference between C and C++, and C is better.

C is probably suited for people who are legitimately interested in going into computer science or software development, i.e. the people who want to put in the time to become better programmers and not just learn how to program for the sake of learning programming.

Which isn't to say that people are wrong to pick Python or Lisp; it's easier to get frustrated with C since it lets you program so closely to the machine. C will take more time to learn than Python and Lisp (I'm a university sophomore and even I don't understand memory allocation very well). But the rewards are immense, and learning any other programming language after learning C will be a breeze. You'll have a much better understanding of how a computer actually works.

It's mostly used for embedded and systems software nowadays, so it won't have as much short-term applicability, but in terms of a long-term payoff it will compensate you handsomely.

You won't have to deal with any of the idiotic syntax or ambiguities found in C++ either. For what it's worth, even Stallman hates C++.

If you have any questions, you can find more information [here](https://www.youtube.com/watch?v=VjGSMUep6_4).