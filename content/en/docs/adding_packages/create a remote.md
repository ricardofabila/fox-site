---
title: "Creating a remote"
description: "Creating a remote file"
lead: "Creating a remote file"
date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
docs:
parent: "adding_packages"
weight: 203
toc: true
---

### How to create a remote

A remote is just a YAMl file that consists of a list of packages. It has the following format:

``` yaml
packages:
- path: "me/hello" # string - GitHub repository with the format OWNER/REPO
  # this is GitHub's standard format
  # just look at the URL of any repo (like this one)
  executableName: "hello" # string - The name you want people to type
  # when using your tool
  type: "binary" # string - Either 'binary' for executables or 'script' for
  # arbitrary scripts (eg. bash scripts)]
  # The following is a list of optional dependencies, may ignore if there are none
  dependsOn:
    - "dependency_name" # - string
```

Example:

``` yaml
packages:
  - path: zyedidia/micro
  executableName: micro
  type: binary
  - path: ricardofabila/rand-stand
  executableName: rand-stand
  type: script
  dependsOn:
    - bun
```

Keep reading to learn how to create a package.
