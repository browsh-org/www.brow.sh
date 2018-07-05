---
title: "In-browser Usage"
permalink: /docs/in-browser-usage/
toc: false
---

To run Browsh in HTTP server mode, use: `browsh -http-server`. By default it runs on port `4333`, so you should then be able to navigate to `localhost:4333` and start browsing.

In this mode you are also able to force the return of plain text responses by setting a special request header:    
`X-Browsh-Raw-Mode: PLAIN`.    
For example:    
`curl --header "X-Browsh-Raw-Mode: PLAIN" localhost:4333/https://google.com`


