---
title: "Secure your email!"
pubDatetime: 2024-08-03T00:00:00Z
modDatetime: 2024-08-03T00:00:00Z
featured: false
draft: false
tags:
  - "Email"
  - "Privacy"
description: ""
---





I have been wanting to write about email security (or securing your personal email) for a very long time now. However, for reasons unknown (procrastination or unclear objectives or laziness), I kept clicking the snooze button on this. Reading and listening to podcasts has given me the nudge and I decided to get back at it.

### What is Email Security?

The idea is simple - to ensure your email is secure and private. Let’s look at it from two angles:

. Personal: This refers to your personal/primary email account. The one that you mostly use for signing up to your social media accounts, subscribe to any magazines, the one that you put on your resume or the one that you use while opening a bank account.
. Professional: This refers to the email account provided to you by your organisation/employer. These emails are generally not used for signing up for a magazine subscription, opening up a social media account or giving to a family member to share something personal with you.

In both these cases, we can think of our valuable data stored in different emails, ranging from personal information, financial information, bank account details or our personal addresses/business confidential data or business plans or strategy documents. With all this valuable information there, would you still want to leave it unprotected or care less about it? 

### Why is it important or why should you care?

Let’s look at some of the ways an email can be misused:

. Phishing attacks: This is one of the most common attack vectors to email accounts and one that organisation(s) pay a good amount to ensure that they are protected from it. What is a phishing email? Put simply, it is an email sent to trick the recipients into giving out sensitive information or clicking on malicious links to download malicious software (or malware) onto their devices that can potentially steal data.
. Spam & spoofing: These are the unwanted messages that we wish we didn’t receive. If your email account is compromised, the attackers can use your account to send spam emails to your contacts. It not only inconveniences them but affects your relationship with them as well. Spoofing is a technique used to send an email pretending to be someone else. In this case, since the email is received from someone the recipient already knows/trusts (you), they would treat it a little less seriously and might end up clicking on the malicious links.
. Malware: Emails can be used to spread malicious software (malware) - software that is designed to damage your system or steal your personal/sensitive information. A popular variant of this is ransomware -  software that is designed to encrypt your personal or professional data and then demand a ransom to receive the decryption key itself (which may or may not happen). These are usually shared in the form of common email attachments such as voice messages, PDF documents or unknown file formats.
. Personal privacy & fraud: Your email may contain personal data or personal communications with your friends and family. Sometimes, it may even include your medical records. Ensuring your email remains secure will ensure any privacy violations and exposure of personal details. If the email you used with your bank gets compromised, an attacker could try to reset your banking credentials (this has become more difficult these days, thanks to improved awareness by the banks) or even attempt a financial transfer. If your social media account has been registered with this email, then an attacker could even change your credentials, thereby not letting you access your account anymore (denial of service) or impersonate you and commit more fraud and cyber crimes online. 
. Reputation: Imagine if your email is compromised and an attacker uses it to send spam or inappropriate content to your contacts. It might not be a good situation to be in. It can take weeks or months to recover from this horrendous situation. If this happens within a professional context, it can lead to significant damage to your professional reputation among your colleagues and indirectly affect your organisation as well. 

### What can we do to improve our email security?

Well, it depends on how much control you want to take over your emails (and more importantly, how much effort you want to put into securing them). To some users, it might not be easy due to the technicality involved in setting up these controls. For a few others, some of these options might not be a feasible solution. From an organisation standpoint, it might include deploying costly tools like a secure email gateway, spam/phishing detection software and so on. In any case, let’s explore some of the options we have to secure our emails:

. Choose a secure email provider
. Enable FA (wherever applicable)

From an organisation or personal domain standpoint, a more comprehensive approach would be to set up the following email security policies from the DNS settings:

. SPF
. DKIM
. DMARC

### . Choosing a secure email provider

This is going to be a tricky & controversial point to expand on. As almost always within the security industry, “it depends” on how you view any email service provider. The most popular email service providers like Gmail, Yahoo or Hotmail/Outlook have historically been under fire for violating user privacy. This does not mean that these services are not secure, but by opting into their free services, we may end up being the product, i.e., we trust them with all our private data with no guarantee that these companies may not use it for any other purposes like creating user profiles or targeting ads or selling our info to third-party data brokers (or more recently, to train their AI models)

It may be possible that we all have a Gmail address because of how popular and easy it was to set it up (whenever you first created your email address). However, if you really want to ensure you get better security and privacy for your data, it might be best to go with one of the other secure email providers. My personal favourite is [Proton](https://proton.me/mail). There are a few other providers like [Tuta](https://tuta.com/), [Mailbox](https://mailbox.org/en/) and [Posteo](https://posteo.de/en).

*Notes: This is not an exhaustive list. I haven’t tested Mailbox and Posteo, although have seen good reviews on them during my research. Between Proton and Tuta, Proton is more user-friendly and feature-rich. It also has other free services that can be accessed with one account, such as a Calendar, VPN, Drive/cloud storage and a Password Manager].* 

### . Enable FA (Two Factor Authentication)

This is comparatively a straightforward activity to enable FA on your email account(s). Most email providers allow setting up FA with the app of your choice, but they are mostly turned off by default. Some of the widely popular applications to set up FA are Aegis, Google Authenticator, Authy, Microsoft Authenticator (for Microsoft accounts) or any password management tool that has the TOTP (Time-based OTP) functionality (Proton Pass for example).

To keep this one short, I’ll write separate posts about the remaining three topics - SPF, DKIM and DMARC. I hope you got some value out of this post and it nudges you to take action to ensure your personal & professional emails remain secure and private! 

If you have any suggestions or feedback, please send me an email [here](mailto:hello@zanil.me).
