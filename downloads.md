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

* Linux Static: [x64]({{base}}_linux_amd64) / [386]({{base}}_linux_386) / [ARMv6]({{base}}_linux_armv6) / [ARMv7]({{base}}_linux_armv7) / [ARM64]({{base}}_linux_arm64)
* Debian/Ubuntu: [x64]({{base}}_linux_amd64.deb) / [386]({{base}}_linux_386.deb) / [ARMv6]({{base}}_linux_armv6.deb) / [ARMv7]({{base}}_linux_armv7.deb) / [ARM64]({{base}}_linux_arm64.deb)
* Redhat/Fedora: [x64]({{base}}_linux_amd64.rpm) / [386]({{base}}_linux_386.rpm) / [ARMv6]({{base}}_linux_armv6.rpm) / [ARMv7]({{base}}_linux_armv7.rpm) / [ARM64]({{base}}_linux_arm64.rpm)
* Arch AUR: 'browsh-bin'. Eg; `yay -S browsh-bin`
* FreeBSD: [x64]({{base}}_freebsd_amd64) / [386]({{base}}_freebsd_386) / [ARMv6]({{base}}_freebsd_armv6) / [ARMv7]({{base}}_freebsd_armv7) / [ARM64]({{base}}_freebsd_arm64)
* OpenBSD: [x64]({{base}}_openbsd_amd64) / [386]({{base}}_openbsd_386) / [ARMv6]({{base}}_openbsd_armv6) / [ARMv7]({{base}}_openbsd_armv7) / [ARM64]({{base}}_openbsd_arm64)
* Mac OSX: `brew tap browsh-org/homebrew-browsh` or [tar.gz]({{base}}_darwin_amd64.tar.gz)
* Windows: [.exe]({{base}}_windows_amd64.exe) (requires Win 10 or newer) (experimental)

* [Checksums]({{base}}_checksums.txt)

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
