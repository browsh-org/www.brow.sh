---
title: Downloads
layout: single
---

{% assign version = site.data.browsh.latest_version %}
{%
  assign base = "https://github.com/tombh/texttop/releases/download/v"
  | append: version
  | append: "/browsh_"
  | append: version
%}

## For latest release: {{ version }}

* [Mac OSX]({{base}}_darwin_amd64)
* [Linux Static]({{base}}_linux_amd64)
* [Debian/Ubuntu]({{base}}_linux_amd64.deb)
* [Arch]({{base}}_linux_amd64.pacman)
* [Redhat/Fedora]({{base}}_linux_amd64.rpm)
* [Windows]({{base}}_windows_amd64.exe)

* [Checksums]({{base}}_checksums.txt)
