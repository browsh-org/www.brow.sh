---
title: "Introduction"
permalink: /docs/introduction
toc: true
---

## What is Browsh?

Browsh is a purely text-based browser that can run in most command line
environments. It updates and renders in realtime so that, for instance, you
can watch videos. It uses the UTF8 half-block trick (▄) to get 2 colours
from every character cell, thus simulating basic graphics. As well as keyboard input it also understands mouse input, for those terminals that support it. So
you can click links and even draw lines in sketch apps.

## Installation

See the [Downloads](/downloads) page.

## Design

Browsh consists of a minimal Golang CLI client and a browser webextension. Most of the work is done by the webextension. When the CLI starts, it looks for a compatible browser (currently only Firefox) and starts it in headless mode. Once
the browser has started it opens a remote debugging connection and installs the extension. It is possible to specify a custom profile if you don't want Browsh interfering with your default profile and settings.

When a web page loads in the browser, custom scripts are injected into the page which then connect to Browsh's background process in the webextension. This background process is itself connected to the CLI client via a websocket.

The per-page content scripts also apply some custom CSS to attempt to make the page conform as closely as possible to the rigid grid of terminal cells. This is not always successful as web pages often carefully position elements to pixel values that aren't units of a character cell -- therefore compromises sometimes need to be made when 2 characters want to occupy the same cell.

To save having to parse every single character's colour and visibility, Browsh uses a custom uni-glyph fullblock font, where every character is: █. Parsing the computed styles for an element is computationally expensive. So instead, to get the colour of a character, the frame builder inspects the pixel value of the page's screenshot that corresponds to the charcter's position. This also has the added benefit of being able to detect a character's visibility without parsing CSS -- if the pixel value changes colour when showing and hiding text, then the character is visible. There are of course edge cases, but their infrequency means that dealing with them is still cheaper than CSS parsing.

The graphics for a frame are generated during the original page's state of hidden text. This screenshot is then scaled to the same size as the active terminal. Those pixel values are then converted to terminal colour escape codes.

Finally the text is layered over the graphics and rendered to the terminal.
