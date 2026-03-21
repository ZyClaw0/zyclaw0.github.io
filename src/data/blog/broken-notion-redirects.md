---
title: "Broken Notion Redirects"
pubDatetime: 2024-05-19T00:00:00Z
modDatetime: 2024-05-19T00:00:00Z
featured: false
draft: false
tags:
  - "Tools"
  - "Updates"
  - "Websites"
description: ""
---





If you have visited my blog in the past few months, you would have come across a popup message with an error message. This has now been fixed!

![blog error.png](Broken%Notion%Redirects/blog_error.png)

### What happened?

I really don’t know! The pop-up message didn’t make any sense to me. Thanks to the smarter people on the internet, I figured that it has something to do with the code that is used in the worker module in Cloudflare. This issue was reported a long time back too, where one of the users [reported](https://github.com/stephenou/fruitionsite/issues/#issuecomment-) it was because of the “Embed Tweet” functionality that broke the integration. However, at that time, some updates from the Notion side had fixed the problem, without having to make any changes in the custom code.

### The fix?

I am not referring to the [book](https://www.goodreads.com/en/book/show/) written by one of my favourite authors David Baldacci (but do give that series a read, if you are into reading mystery/crime/thriller fiction novels), but I was lucky enough to find a solution online. It was simply to comment a few lines of code in the worker code and the issue is no more! 

```jsx
// The solution:-
// . Commenting the MetaRewriter class
// . Commenting the  lines that referenced this class 
//    within the appendJavascript method

// Those lines of code were looking for some attributes from Twitter, 
// which relates back to the issue reported four years ago
```

Credits to [devarxify](https://github.com/devarxify) (and to the original unknown author) for the fix which you can find [here](https://github.com/stephenou/fruitionsite/issues/#issuecomment-).
