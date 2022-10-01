---
title: "Adding a remote"
description: "Adding a remote"
lead: "Adding a remote"
date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
docs:
parent: "adding_packages"
weight: 202
toc: true
---

This section is designed to show you how to set your package in a way that it can be installed with fox.

{{< details "💡 There is an official remote with hand-cured packages that you can install right away." >}}
You can find it  <a href="https://github.com/ricardofabila/fox-packages" target="_blank">
here</a>. If you have a cool package that you want to share with the whole world, feel free to submit a PR, and I'll
gladly check it out.
{{< /details >}}

### How to make my package installable with fox

To install a package, first `fox` needs to know where to find it. To achieve this, you need to add a `remote` to your
repositories file, which is located at `~/.fox/repositories.yaml`.

The __remotes__ section of this YAMl file consists of a list of items with the following format:

``` yaml
remotes:
- url: "" # string - a url where to find a packages YAML file
  type: "github" # string - either 'open' or 'github'
```

The value for `url` is a _string_ that fox will use to look for a YAMl file with your packages. The value for `type` is
a _string_ that can be either _github_ or _open_. Use _open_ if the url is public (eg. on your own server, an S3 bucket,
etc), or use _github_ if the file is hosted on a private/public GitHub repo.

Example `~/.fox/repositories.yaml`:

``` yaml
remotes:
- url: "repos/<OWNER>/<REPO_NAME>/contents/packages.yaml"
  type: "github"
- url: "https://raw.githubusercontent.com/ricardofabila/test/main/repositories.yaml"
  type: "open"
```

__Note__: notice how the the url for the _github_ type is not a full url, but a GitHub path.

You can edit the file directly using your preferred editor to add remotes, but you can also use the following command:

```bash
  fox add remote --url "the url" --type "open|github"
```

Use `fox add remote -h` for help.

Continue to know what this _remote_ file consists of.
