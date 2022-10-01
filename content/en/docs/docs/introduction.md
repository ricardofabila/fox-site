---
title: "Introduction"
description: "fox is a tool helps you install packages from private (and public) GitHub repositories"
lead: "<code>🦊 fox</code> is a tool helps you install packages from private (and public) GitHub
repositories. <br/><br/> If you have a tool that you want to share with the rest of your team (or the entire world)
, <code>fox</code> makes it trivial to do it."
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "docs"
    identifier: "docs-introduction"
weight: 100
toc: true
---

### What does fox do?

- Makes is trivial to install a package form a GitHub repository even if it's private. Fox packages are just GitHub
  releases, as long as you have read access to a repo, you can install (pretty much) anything you want.
- Fox installs packages to a specific directory `/usr/local/bin/Fox/bin` (on macOS and linux systems). It won't install
  anything outside that directory.
- Trivially create your own packages. To add your repo to the available packages list, all you need to do is edit a
  **yaml** file. That's it!

### What fox does NOT do?

- Requires you te learn a whole new set of [made up words](https://www.youtube.com/watch?v=GWERB5GNExY) to use.
- Run post-install scripts that may do something nasty to your machine.

Check the **Quick Start →** section to learn more.
