---
title: "Creating a package"
description: "Creating a script and binary package"
lead: "Creating a remote file"
date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
docs:
parent: "adding_packages"
weight: 204
toc: true
---

### How to create a package

Finally, to make your package installable, all you need it to have a GitHub **release** (not a _draft_) for it.

1. Make sure your repo has a **release** with attached assets. Right now only binary executables and scripts (Eg. bash
   scripts) are supported. They can be contained in a zip/tarball or be at the root level.

> If your package is an **executable**, make sure your release has the binaries with the appropriate name for the OS and
> the architecture. It doesn't have to be perfect as `fox` will try to fuzzy search for the best match. Normally this
> are created for you if you use a build tool (eg. [goreleaser](https://goreleaser.com/install/))

Example:

``` yaml
- mypkg_darwin_amd64_v1
- mypkg_darwin_arm64
- mypkg_linux_386
- mypkg_linux_amd64_v1
- mypkg_linux_arm64
- mypkg_windows_386.exe
- mypkg_windows_amd64_v1.exe
- mypkg_windows_arm64.exe
```

> If your package is a **script**. Just have the script file in the repository with the name you choose as
> your `executableName` in the YAML entry. Take a look at [rand-stand](https://github.com/ricardofabila/rand-stand) as
> an example.
>
> Alternatively, you can have the script file in the assets with the name you choose as your `executableName` in the
> YAML entry. This is useful if you don't have the final script file in the repo contents, as it may get build in
> some sort of bundling phase (eg: you use emacs to write your script using literate programing and have the final
> script created with some command).

Example:

``` yaml
- myscript.sh
```

2. Add your package to your `remote` file following the format described in the example on the "Creating a remote"
   section:

Example of your remote YAML file:

``` yaml
packages:
- path: me/bff
executableName: bff
type: binary
dependsOn:
  - curl
- path: company-name/a-tool
executableName: tool
type: script
dependsOn:
  - wget
  - zsh
```

And that's it! Now you can run:

``` bash
fox install tool
```

##### Can I test how my package will be installed before adding it to the file?

Of course, you can! In your `~/.fox/repositories.yaml` file, there is a section called `packages`. That section is a list
of packages. It follows the exact format described above.

You can use this section to add you package locally and test how `fox` will install it. Very useful if you want to test
that you did everything right when creating your release.

Example:

In your `~/.fox/repositories.yaml`:

``` yaml
packages:
  - path: me/my-thing
  executableName: my-thing
  type: binary
  dependsOn:
    - curl
```

And now you can run the following to make sure you did every thing right:

``` bash
fox install my-thing
```

