---
title: "1.1.1.1 for Families"
pubDatetime: 2020-04-15T00:00:00Z
modDatetime: 2020-04-15T00:00:00Z
featured: false
draft: false
tags:
  - "DNS"
  - "Websites"
description: ""
---

# 1.1.1.1 for Families




<!-- Image: 1dot.png -->

If you haven't heard of `1.1.1.1` (or commonly known as 1 dot) before, it is a fast and secure DNS resolver provided by *Cloudflare,* and its free of cost. Its popularity has grown so much so that it has become the second largest DNS resolver after Google.
Since they have become very popular, on 1st April 2020, they have launched 1 dot for families. The primary objective of their new DNS resolvers are to filter out bad sites and to keep adult content from being accessed by kids. Their two new offerings are `1.1.1.2` (malware) and `1.1.1.3` (malware and adult content). 

If you're using IPv4, then you can configure using these settings:

- Malware Blocking Only
    - Primary DNS: `1.1.1.2`
    - Secondary DNS: `1.0.0.2`
- Malware and Adult Content
    - Primary DNS: `1.1.1.3`
    - Secondary DNS: `1.0.0.3`

If you're using IPv6, then you can configure using these settings:

- Malware Blocking Only
    - Primary DNS: `2606:4700:4700::1112`
    - Secondary DNS: `2606:4700:4700::1002`
- Malware and Adult Content
    - Primary DNS: `2606:4700:4700::1113`
    - Secondary DNS: `2606:4700:4700::1003`

During the current situation where many are confined to our homes and working remotely, these settings can provide a better security and enhance your privacy online. You can find the original blog post from Cloudflare [here](https://blog.cloudflare.com/introducing-1-1-1-1-for-families/).
