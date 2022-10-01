---
title: "Introduction"
description: "Learn how to make your package installable with fox"
lead: "Learn how to make your package installable with fox"
date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
  docs:
    parent: "adding_packages"
    identifier: "adding_packages-introduction"
weight: 201
toc: true
---

This section is designed to show you how to set your package in a way that it can be installed with fox.

{{< alert icon="💡" text="The instructions apply no matter if your package is public or private." />}}

### Introduction

Let's say that you created a useful tool, and you want to share it with others.

For example: you made a bash script that renames files in a folder to a standard format, and you want to share it with
your coworkers.

You create a repo for it. Add some detailed installation instructions to the README.md and make sure it is in a nice
format.

However, as you might expect, not everybody reads the manual. Or your team has people that are not that tech-savy and
don't know how to move something to `/usr/local/bin` or what a symlink is.

The truth is: people like (expect) one-liner instructions. You could try to create an installer script for your tool,
but having to create one might even be more work than creating your original script was!

Plus, how do you deal with updates for new features and bug fixes. Do you send a _@here_ message in slack to let
everybody know that you pushed an update? Do you really think people will read it and pull the changes?

That's when you try to add your little script to an existing package manager, but since it is private, you quickly learn
how hard it is to do so.

You need to create a ruby file (🤮), learn all sort of [made up words](https://www.youtube.com/watch?v=GWERB5GNExY), ask
people to create special files ot set env vars for tokens, and that's just the beginning.

There has to be a better way. It shouldn't be that hard.

There is a better way, you can use `fox` to help you. The gist of the process is:

- You create a GitHub repo for your package
- You create a release for it
- You create a YAML file with some information about your packages
- Your team adds one line to a config file
- And that's it! Now they can install and update your tool with one command

Go to the next page to learn how to make your package installable with `fox`.
