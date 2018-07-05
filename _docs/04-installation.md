---
title: "Installation"
permalink: /docs/installation/
toc: true
---

{% assign version = site.data.browsh.latest_version %}

Browsh's only prerequisite is a current (57+) version of Firefox. Once you have that you can [download](/downloads/) the appropriate binary or package for your system.

Packages such as the `.deb` and `.rpm` versions provide a new `browsh` command. The static binaries however need to first be made executable; `chmod a+x browsh_{{ version }}_linux_amd64`. You will then be able to run the Browsh TTY client with: `./browsh_{{ version }}_linux_amd64`.

The HTTP service can be started with: `./browsh_{{ version }}_linux_amd64 -http-server`

## Docker

A Docker image is available that bundles an up to date version of Firefox, so that everything you need to run Browsh is self-contained. You can pull and run the TTY client with: `docker run browsh-org/browsh`
