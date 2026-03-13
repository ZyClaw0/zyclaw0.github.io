---
title: "Sublist3r - subdomain enumeration"
pubDatetime: 2019-01-26T00:00:00Z
modDatetime: 2019-01-26T00:00:00Z
featured: false
draft: false
tags:
  - "Subdomain"
  - "Terminal"
  - "Tools"
description: ""
---

# Sublist3r - subdomain enumeration




Sublist3r is an information gathering tool written in python for subdomain enumeration. This tool uses OSINT or Open Source Intelligence to gather information from various search engines such as Google, Yahoo, Baidu, Bing and so on.

The tools is available on GitHub which can be setup by cloning the git repository as below:
`git clone <https://github.com/aboul3la/Sublist3r`

Sublist3r also requires some additional packages to function correctly. Although, this could be setup already, it is always a good idea to install them using the command [use sudo if logged in as user]:
`(sudo) pip install -r requirements.txt`

Sublist3r also provides various options that can be configured such as specifying search engine using `-e` or to scan for ports on target using `-p`. A brute force option is also available using the option `-b`, although it might take more time to retrieve results. The search results can be saved to file using the  `-o` option.
`python sublist3r.py -d domain.com -o output.txt`

This would list most of the subdomains for the provided domain. You can find more about Sublist3r from [GitHub](https://github.com/aboul3la/Sublist3r).

---

🏠

---