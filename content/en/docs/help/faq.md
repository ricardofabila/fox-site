---
title: "FAQ"
description: "Answers to some frequently asked questions."
lead: "Answers to some frequently asked questions."
date: 2020-10-06T08:49:31+00:00
lastmod: 2020-10-06T08:49:31+00:00
draft: false
images: []
menu:
docs:
parent: "help"
weight: 301
toc: true
---

### Why another package manager

Because it was easier for me to create a new package manager from scratch than to add a private repo to homebrew. Also,
fox works on linux, while I have never seen anyone successfully install homebrew on a linux system and actually use
it. Trust me, I tried.

### Do I need to have a remote YAML file if I have repos on my own that I want to install via fox

No. In your `~/.fox/repositories.yaml` file there is an entry called `packages` which you can use to add a package that
you want to be able to install via fox. It can even be a GitHub repo that doesn't even know that fox exists! As long as
it has releases that comply with what fox expects (which is what most package managers expect), you can install it via
fox 😜.

This is useful too if you have a private packages of your own, and you want to make it easy to install them on different
systems.

### I have a public package that I want to make installable via fox for everyone

Fox has an official repositories list that fox knows to look for by default. If you have a public package that you want
to add it to the list, feel free to open a PR on this repo with your entry to the YAML file. Attach links to the GitHub
repo, and a short description of what your package does, and I'll add it to the list.

{{< alert icon="💡"
text="You can find it at <a href=\"https://github.com/ricardofabila/fox-packages\" target=\"_blank\">here</a>" />}}

### Why not Windows support?

Because I have not used a Windows machine in many years. While windows does a few things better than unix systems, the
way it handles its PATH is not one of them. Having it being a GUI thingy is too cumbersome. I am not saying that a
colon-separated ENV string is a good alternative. It is not! But at least it is _easier_ to manage.

I know there is a way to do it programmatically, but since I have no easy access to a Windows machine at the moment, I
just can't do it right now. Feel free to use the tip button, so I can get one sooner 😜.

In all seriousness, I do plan to add Windows support and work on a VM, but is not the highest priority right now.

### Are private repos only supported?

No. You can add public repos just the same way as a private repo. fox uses the official gh CLI, so as long as you can
see the repo you want to install from. You are good to go.

#### Why no post-install scripts support?

While most packages use post-install scripts for normal things like updating man pages, and such. Arbitrary code
execution without the user's explicit approval is something I am quite firmly against. This is one of the reasons I
don't like NPM. While it does offer a flag to turn that off, if you do, most packages stop working completely. This is also
the reason why if you run `brew install` with `sudo` it yells at you.

I am not letting `fox` to allow someone to add a post install script that has `rm -rf /` in it. Even by accident.

Perhaps in the future I can add support for post-install scripts, but since fox was conceived specifically for private
repos, it is not a priority. you can let your team know if they need to do something post installation in the README or
something.

The worst thing that could happen is that `fox` gets wide adoption with a fundamental flaw just because I didn't put
enough though about the implications. This is how we got stuck with things that are massively used but are simple wrong
and shouldn't exist they way they do. Things like: NPM, Java,
JavaScript, [unix](https://www.youtube.com/watch?v=L9v4Mg8wi4U), AngularJS, Object Oriented Programming, PHP, Vladimir
Putin, and many more. I am sure that the creators of these things didn't intend these things to have the wide adoption
that they do while never being able to fix the fundamental flaws they missed on the early stages.

I already have a few ideas on how to tackle this, but it still in the early stages.
