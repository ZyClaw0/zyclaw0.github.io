---
title: "Installing Nessus"
pubDatetime: 2020-11-23T00:00:00Z
modDatetime: 2020-11-23T00:00:00Z
featured: false
draft: false
tags:
  - "Nessus"
  - "Tools"
  - "Vulnerability scanners"
description: ""
---

# Installing Nessus




One of the most common vulnerability assessment tool available is Nessus, by Tenable. It was on my *To Do* list for a while, especially after I came across Qualys community edition [scanner](https://www.qualys.com/community-edition/), which allows for unlimited vulnerability scanning for one application URL. As Qualys provides a cloud-based scanner, they only require you to register for a free account and get moving from there.

So today, I decided to install Nessus and give it a try. In this post, I will describe the installation process. In my case, I am going to install it on my Kali machine (2020.4).

Nessus provides an "Essential" plan that allows students and those starting their cyber security career or anyone interested to use the product, to scan up to 16 unique IP addresses (after going through the Nessus UI, I learned that after 90 days of the last scan of a host or an IP, it will not count against the limit of 16 - which is a nice feature they offer). If it is for professional use, it would be better off to upgrade to a "Professional" [plan](https://www.tenable.com/products/nessus) as that would provide more advanced features (such as perform compliance checks or content audits, live results or use the Nessus virtual appliance)

### Step 1: Register for an activation code and download Nessus

Navigate to the registration page [here](https://www.tenable.com/products/nessus/nessus-essentials) and register for an activation code that will be sent to the email address provided. Upon successful registration, you'll be redirected to a page where you can download the installer as well. You can also directly navigate to the downloads page [here](https://www.tenable.com/downloads/nessus) and register for an activation code during the setup phase later as well. Ensure that you download the correct version listed on the downloads page. You can use the command `uname -a` to check your architecture. I downloaded the following version from my Kali machine:

<!-- Image: nessus00.png -->

### Step 2: Install and start the service

Once the download is complete, navigate to the "Downloads" folder or to the location you saved the file. (Note: With Kali 2020.4, the default shell is based on zsh and not bash. It allows changing directory just by entering the path and does not require the cd command, although that would work as well). Next, use the `dpkg` command as the root user if you are not (which you should not be unless required). It is a quick install and does not take too long for it to complete. Once the installation is completed, you need to start the Nessus service using the `systemctl` command.

<!-- Image: nessus01.png -->

<!-- Image: nessus02.png -->

### Step 3: Navigate to the Nessus UI to activate and finish the installation

By default, the Nessus UI is accessible on port 8834 and so, navigating to `https://localhost:8834/` should greet you with a welcome page and the setup prompt (Note: Since you are hosting this on a personal workspace and it doesn't have an SSL certificate by default, you would receive a warning which you may accept and continue).

<!-- Image: nessus03.png -->

<!-- Image: nessus04.png -->

After choosing the product plan, Nessus Essentials, in this case, you can use the activation code and details received during Step 1 and complete the activation process. If at all you have not got an activation code yet or you did not register during Step 1 earlier, you can register for an activation code from here as well. After completing the registration process, you are ready to start using Nessus.

<!-- Image: nessus05.png -->

Hopefully, the installation process went well and you are now able to use, learn and play around with Nessus. In a future post, I will go through the various scanning options and settings available in the Nessus Essential Plan. If you have any feedback or find any silly errors, please do leave a comment or get in touch.

---



---