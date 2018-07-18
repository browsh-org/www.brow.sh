---
title: "Mosh is better than SSH"
permalink: /docs/mosh/
---

[Mosh](https://mosh.org/) is a modern replacement for SSH that has much better support for slow and unstable networks such as those typically found over mobile networks.

Its main advantage for Browsh is that it only sends screen diffs, therefore it only uses bandwidth when something on the screen changes. However the fact that Mosh also uses UDP is also useful, as UDP is more lenient to lost data, which Browsh itself also generally tolerates. Then of course there are the advantages of IP roaming, so that when your IP changes, such as travelling on a train with a mobile network, connections aren't dropped.

In order to use Mosh with true colour support (which is a requirement for Browsh's colour mode), you currently need to use Mosh's master branch, which means compiling it.

```
$ git clone https://github.com/mobile-shell/mosh
$ cd mosh
$ ./autogen.sh
$ ./configure
$ make
$ make install
```

Mosh needs to be installed both on your local machine and your remote server. Though note that the local Mosh client is available on Android ([JuiceSSH](https://play.google.com/store/apps/details?id=com.sonelli.juicessh), [Termux](https://play.google.com/store/apps/details?id=com.termux)), in the [Chrome Browser](https://chrome.google.com/webstore/detail/mosh/ooiklbnjmhbcgemelgfhaeaocllobloj) and iOS's [Blink Shell](https://itunes.apple.com/app/id1156707581).

There is no special setup to run Browsh over Mosh, as long as you have them both installed on your remote server. Though note that Mosh does require port `60000` (and upwards if you'll be running more than one simultaneous session). Once logged in through Mosh you will be able to run `browsh` normally as if you were on your local command prompt.
