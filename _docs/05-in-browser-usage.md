---
title: "In-browser Usage"
permalink: /docs/in-browser-usage/
toc: true
---

The in-browser service allows you to use Browsh in a browser, rather than in a client. However currently it doesn't have the same features of the TTY client, for example, there are no realtime updates to page contents and you can't login to sites. Its advantages are firstly that browsers are more common and easily accessible than terminals, and secondly that returned pages don't require further bandwidth to scroll.

To run Browsh in HTTP server mode, use: `browsh --http-server-mode`. By default it runs on port `4333`, so you should then be able to navigate to `localhost:4333` and start browsing.

In this mode you are also able to force the return of plain text responses by setting a special request header:    
`X-Browsh-Raw-Mode: PLAIN`.    
For example:    
`curl --header "X-Browsh-Raw-Mode: PLAIN" localhost:4333/https://google.com`

