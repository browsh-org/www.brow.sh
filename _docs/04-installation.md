---
title: "Installation"
permalink: /docs/installation/
toc: true
---

{% assign version = site.data.browsh.latest_version %}

Browsh's prerequisites are a current (57+) version of Firefox and [a terminal client that supports true colour](https://gist.github.com/XVilka/8346728). Once you have those you can [download](/downloads/) the appropriate binary or package for your system.

Note that the following examples all use x64 packages. Please use the proper package for your architecture.

## Debian/Ubuntu
```
wget https://github.com/browsh-org/browsh/releases/download/v1.4.12/browsh_1.4.12_linux_amd64.deb
sudo apt install ./browsh_1.4.12_linux_amd64.deb
rm ./browsh_1.4.12_linux_amd64.deb
browsh
```

Packages such as the `.deb` and `.rpm` versions provide a new `browsh` command.
So too does the Homebrew command (for OSX users only):    
`brew tap browsh-org/homebrew-browsh`

The static binaries however need to first be made executable; `chmod a+x browsh_{{ version }}_linux_amd64`. You will then be able to run the Browsh TTY client with: `./browsh_{{ version }}_linux_amd64`.

Browsh can then be run with something like: `./browsh_{{ version }}_linux_amd64`

## Docker

A Docker image is available that bundles an up to date version of Firefox, so that everything you need to run Browsh is self-contained. You can pull and run the TTY client with:    
`docker run -it --rm browsh/browsh`
