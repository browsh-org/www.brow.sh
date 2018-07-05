---
title: "Terminals"
permalink: /docs/terminals/
toc: true
---

Generally most modern terminals should at least show *something*. A quick little
tip is that you can always toggle in and out of monochrome mode with `ALT+m`. It removes all graphics and just uses your terminal's default foreground and background colours.

The best resource for up to date information on true colour support across both
terminals and multiplexors (like `tmux` for example) is this [gist](https://gist.github.com/XVilka/8346728). However true colour support does not necessarily mean
that Browsh will then have full-functionality. Some terminals may have other issues, such as mouse input or UTF-8 rendering problems.

At the very least you should ensure you have a monospaced font in your terminal. This is almost always the case by default. Even so, you may still wish to change the font, or at least the font settings, to better support the UTF-8 half block (▄), which is responsible for rendering Browsh's graphics. There are 3 main issues you need to look out for:

  1. The font simply doesn't contain the UTF-8 half block character. Most of the fonts here at Github's [ProgrammingFonts/ProgrammingFonts](https://github.com/ProgrammingFonts/ProgrammingFonts) repo have it, so consider changing.
  2. The font's glyph for the UTF-8 half block character isn't actually a true half-block, usually it's slightly smaller, this causes thin empty bands to appear on the page. I don't find this a big issue, but if you want perfection then first consider the next point or try a different font.
  3. Your terminal doesn't align fonts perfectly in their cells. Some terminals allow you to change things like the padding around characters or their X and Y offset. Try playing with these settings to remove any banding artefacts.

## Known working terminals

  * Alacritty
  * iTerm
  * Konsole


