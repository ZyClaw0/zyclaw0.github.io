# Is BGP safe?

Date: 19/04/2020
Tags: Web Sec, Websites

Cloudflare recently published a new site that can check if your ISP is using security measures to route the traffic over the internet. [Is BGP Safe Yet](https://isbgpsafeyet.com/) checks whether your Internet Service Provider (ISP) has security filters and measures in place that can make BGP stable and secure.

There are interactive diagrams on the page where you can see how a BGP request would travel under normal conditions and if it is hijacked as shown below:

![BGP1.png](Is%20BGP%20safe/BGP1.png)

![BGP2.png](Is%20BGP%20safe/BGP2.png)

![BGP3.png](Is%20BGP%20safe/BGP3.png)

### How are they doing it?

The site offers a valid and an invalid route for loading pages from the internet. If your ISP identifies the bad route and only goes through the valid route, it passes the test. Otherwise, if both the routes are accepted by the ISP, then it implies that your ISP isn't filtering the bad routes.

### What is BGP anyway?

BGP or **B**order **G**ateway **P**rotocol is one of the important routing protocol that is responsible for the internet to function properly. An Autonomous System (or AS) is a network or collection of networks that is managed by one or more network providers or an organisation. BGP is responsible for routing the data from one AS to another through the internet based on shortest route and few other preferences/settings of the AS's. In other words, BGP gets the content delivered through the big ocean, that is the internet.

### Is it dangerous or should you care?

Well, yes. If these BGPs are accidentally advertising wrong routes or if they are hijacked by malicious actors, then there could be severe consequences. There are a few cases of this happening in the past where there was a large scale outage of various websites. If it is hijacked, it could be for spying or performing a Denial Of Service (DOS) attack.

It would be great when all the ISPs and other internet giants implements the necessary measures (a certification system called *RPKI* or **R**esource **P**ublic **K**ey **I**nfrastructure) to ensure BGP routing is secure. You can find more about RPKI from the Cloudflare blog [here](https://blog.cloudflare.com/rpki/). Until then, lets wait and hope there isn't another BGP leak on the internet anytime soon.

---

[🏠](../../Welcome%20to%20ZyBlog%20133984b8ad578073b4b6e62800ce71c3.md)

---