---
title: "Install a public package"
description: "Installing public packages"
lead: "Installing public packages"
date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
docs:
parent: "adding_packages"
weight: 205
toc: true
---

### How to install a public package

Incidentally, using the `packages` list in your local repositories file, you can install packages that are on GitHub but
the auth didn't add it to a package manager*. All without needed the package authors to even know that `fox` exists. As
long as their releases follow a pattern that `fox` can understand (which is the same pattern most package managers use),
you should be able to do it (exceptions apply).

We can use this [repo I randomly found](https://github.com/metadelta/mdlt) as an example:

``` yaml
packages:
  - path: metadelta/mdlt
    executableName: mdlt
    type: binary
```

You can edit the `~/.fox/repositories.yaml` file manually, or you can run the command to do it automatically:

```bash
fox add package --path "metadelta/mdlt" --type "binary" --executableName "mdlt"
```

And now you can do `fox update` and then a quick `fox install mdlt` and bam! You have it without the author needing to
do anything.

\* I can't blame them, it is unnecessary difficult; specially for private repos. That's why I made `🦊 fox` in the first
place. It was easier to create a new package manager that works on macOS and linux than to add my CLI tool to HomeBrew
because it was a private repo.
