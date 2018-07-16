---
title: "Adding Extensions"
permalink: /docs/extensions/
toc: true
---

It's possible to add any of Firefox's extensions, for example adblockers, etc. There are 2 methods to do so.

## Manual installation

You can manually download an extension's `.xpi` file and then copy it to the appropriate Firefox profile path. For detailed instructions, see this Stack Overflow [answer](https://stackoverflow.com/questions/37728865/install-webextensions-on-firefox-from-the-command-line).

## GUI installation

If you are running Browsh in a GUI environment, like your own laptop or dekstop then you can simply run Browsh using:    
`browsh -with-gui`. This will open Firefox using the same profile that Browsh uses, so that any changes you make will also take effect in Browsh. Adding extensions this way is exactly the same as you would in normal Firefox, you go to the extension's webpage and click "+ Add to Firefox".
