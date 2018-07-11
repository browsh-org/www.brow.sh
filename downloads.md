---
title: Downloads
layout: single
---

{% assign version = site.data.browsh.latest_version %}
{%
  assign base = "https://github.com/browsh-org/browsh/releases/download/v"
  | append: version
  | append: "/browsh_"
  | append: version
%}

## For latest release: v{{ version }}

* Linux Static: [x64]({{base}}_linux_amd64) / [ARM]({{base}}_linux_armv6)
* Debian/Ubuntu: [x64]({{base}}_linux_amd64.deb) / [ARM]({{base}}_linux_armv6.deb)
* Redhat/Fedora: [x64]({{base}}_linux_amd64.rpm) / [ARM]({{base}}_linux_armv6.rpm)
* Free BSD: [x64]({{base}}_freebsd_amd64.deb) / [ARM]({{base}}_freebsd_armv6.deb)
* [Mac OSX]({{base}}_darwin_amd64.tar.gz)
* [Windows]({{base}}_windows_amd64.exe)

* [Checksums]({{base}}_checksums.txt)

## Homebrew

`brew tap browsh-org/homebrew-browsh`

Note that you need to have Firefox 57 or newer installed
