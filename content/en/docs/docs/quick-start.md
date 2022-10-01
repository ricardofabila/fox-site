---
title: "⚡ Quick Start"
description: "This small section is meant to help you get started in no time."
lead: "This small section is meant to help you get started in no time."
date: 2020-11-16T13:59:39+01:00
lastmod: 2020-11-16T13:59:39+01:00
draft: false
images: []
menu:
docs:
parent: "docs"
weight: 110
toc: true
---

#### Dependencies:

##### ⚓ Required

This tool is as zero-dependencies as it can possibly get.

- [GitHub CLI](https://cli.github.com) to install packages. Don't worry if you don't have it already, just follow the
  installation instructions below; you can run `fox gh` to install it 😉.

That's it. Seriously, you don't need to install anything more.

{{< details "Why the GitHub CLI?" >}}
In order to install packages from private repos, you need to have an access token. GitHub's official CLI manages these
automatically for you.

Plus, GitHub APIs are [rate-limited](https://docs.github.com/en/rest/overview/resources-in-the-rest-api#rate-limiting)
when using them anonymously to avoid abuse, by using the `gh` CLI we can avoid any issues.
{{< /details >}}

---

## Installation

Getting started is as easy as 1, 2, 3.

1.) Just run:

```bash
sudo curl -fsSL "install.getfox.sh" | bash
```

Follow the on-screen instructions to add `fox` to your _$PATH_.

2.) Install the official [GitHub CLI](https://cli.github.com/), if you don't already have it. Relax, you can run `fox gh`
   to install it 😉. Then run `gh auth`. To setup authentication. I recommend using _ssh keys_, so you never have to
   use a password.

3.) That's it! That wasn't so bad, was it?

If you did everything correctly you can try running the following command:

```bash
fox doctor
```

This will check your environment for potential problems and possible enhancements.

## How to install packages

There are lots of amazing packages in the central repository of public packages installable by `fox` (find
it [here](https://github.com/ricardofabila/fox-packages)).

Just run the following command to see the list:

```bash
fox list
```

Once you have a package that you want to install, just do a quick:

```bash
fox install <package-name>
```

And presto! You installed your first package.

## Go further

Learn how to make your own packages installable using `fox` in the next section.
