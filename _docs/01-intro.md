---
title: "Introduction"
permalink: /docs/introduction/
toc: true
---

## What is Browsh?

Browsh is a purely text-based browser that can run in most TTY terminal
environments and in any browser. The terminal client is currently more advanced
than the browser client.

### TTY client
The terminal client updates and renders in realtime so that, for instance, you
can watch videos. It uses the UTF8 half-block trick (▄) to get 2 colours
from every character cell, thus simulating basic graphics. As well as keyboard input it also understands mouse input, for those terminals that support it. So
you can click links and even draw lines in sketch apps.

### Browser client
The browser client, somewhat confusingly, renders simple HTML or plain text that
itself was parsed by Browsh running inside another browser. The point being that the HTML or text that Browsh outputs is extremely lightweight. As of writing in 2018, the
average website requires downloading around 3MB and making over 100 individual HTTP requests. Browsh will turn this into around 15kb and 2 HTTP requests - 1 for the HTML/text and the other for the favicon.

Currently the HTML/text output is not updated in real time nor interactive, the hope is that the Browser client will eventually have feature parity with the TTY client.

## Installation

See the [installation](/docs/installation/) page.

## Design

Browsh consists of a minimal Golang CLI client and a browser webextension. Most of the work is done by the webextension. When the CLI starts, it looks for a compatible browser (currently only Firefox) and starts it in headless mode. Once
the browser has started it opens a remote debugging connection and installs the extension.

When a web page loads in the browser, custom scripts are injected into the page which then connect to Browsh's background process in the webextension. This background process is itself connected to the CLI client via a websocket.

The per-page content scripts also apply some custom CSS to attempt to make the page conform as closely as possible to a rigid grid as is enforced by terminal cells. This is not always successful as web pages often carefully position elements to pixel values that aren't units of a character cell -- so compromises sometimes need to be made when 2 characters want to occupy the same cell.

To save having to parse every single character's colour and visibility, Browsh uses a custom uni-glyph fullblock font, where every character is: █. Parsing the computed styles for an element is computationally expensive. So instead, to get the colour of a character, the frame builder inspects the pixel value of the page's screenshot that corresponds to the charcter's position. This also has the added benefit of being able to detect a character's visibility without parsing CSS -- if the pixel value changes colour when showing and hiding text, then the character is visible. There are of course edge cases, but their infrequency means that dealing with them is still cheaper than CSS parsing.

In the case of the TTY client the graphics for a frame are generated during the original page's state of hidden text. This screenshot is then scaled to the same size as the active terminal. Those pixel values are then converted to terminal colour escape codes. Finally the text is layered over the graphics and rendered to the terminal.
