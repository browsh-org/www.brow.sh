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

You need to have Firefox 57 or newer installed. For the TTY client you need to have a
terminal with [true colour support](https://gist.github.com/XVilka/8346728).

## For latest release: v{{ version }}

* Linux Static: [x64]({{base}}_linux_amd64) / [ARM]({{base}}_linux_armv6)
* Debian/Ubuntu: [x64]({{base}}_linux_amd64.deb) / [ARM]({{base}}_linux_armv6.deb)
* Redhat/Fedora: [x64]({{base}}_linux_amd64.rpm) / [ARM]({{base}}_linux_armv6.rpm)
* Free BSD: [x64]({{base}}_freebsd_amd64.deb) / [ARM]({{base}}_freebsd_armv6.deb)
* [Mac OSX]({{base}}_darwin_amd64.tar.gz)
* [Windows]({{base}}_windows_amd64.exe) (experimental)

* [Checksums]({{base}}_checksums.txt)

## Homebrew

`brew tap browsh-org/homebrew-browsh`


## FAQs

**It's not fast or saving me bandwidth**    
Browsh's main usecase is to be run on a remote server, such as a cloud VM, where there is
fast and cheap bandwidth. You can then access Browsh's output over any normal SSH client
or better yet [Mosh](https://mosh.org/) (though note that self-compiling Mosh is currently needed to get true colour support). You can also access Browsh's output via a normal browser by running Browsh in HTTP mode: `browsh --http-server-mode`.

**It doesn't work on Windows**    
This is a known bug, it's not been a top priority because of the main usecase described
in the previous FAQ answer here. Please follow this [Github issue](https://github.com/browsh-org/browsh/issues/32) for updates.

**It works but the graphics has long black lines in it**    
Your terminal doesn't support true colour, see here for more details: [https://gist.github.com/XVilka/8346728](https://gist.github.com/XVilka/8346728)
