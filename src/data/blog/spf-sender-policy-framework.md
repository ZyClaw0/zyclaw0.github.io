---
title: "SPF - Sender Policy Framework"
pubDatetime: 2024-09-21T00:00:00Z
modDatetime: 2024-09-21T00:00:00Z
featured: false
draft: false
tags:
  - "DNS"
  - "Email Security"
description: ""
---

# SPF - Sender Policy Framework




SPF is one of the foundational elements of email authentication for DMARC. This email authentication technique is used to verify that the sender is the person who we expect them to be. This helps in validating the authenticity of an email that we receive. The standard protocol used for email, the Simple Mail Transfer Protocol (SMTP) does not perform this validation and hence we use SPF.

For example, if you receive an email from alice@acme.org, SPF helps in ensuring that:

1. Alice was the one who sent you that email and it was not forged
2. This email is not marked as spam by your email service provider

If you own a personal domain (or manage an organisation’s domain), then SPF will help ensure that your emails don’t get marked as spam, they are  delivered to the intended recipient and nobody else can pretend to be you! 

It is worth noting that there are valid use cases where you may want somebody else to send emails on your behalf like marketing emails or for automation purposes. In these cases, we need to ensure that our configurations include these services so that they are not marked as spam by the recipient’s mail servers.

### Sample SPF record

Here is a sample SPF record added to the DNS settings:

`v=spf1 ip4:192.0.1.1 ip4:192.0.1.2 include:mailesender.com -all`

| v=spf1 | This value specifies the SPF version number to be used |
| --- | --- |
| ip4:192.0.1.1 ip4:192.0.1.2 | The next section specifies the IP address(es) of your email servers |
| include: mailsender.com | The following section may include any third-party organisations who are authorised to send on your behalf. In this case, the SPF for [mailsender.com](http://mailsender.com) will be checked and all those IP addresses/domains will be considered as authorised to send an email on your behalf |
| -all | This specifies that addresses not listed in SPF are unauthorised and should be rejected. 
The alternate option here is to use `~all` which specifies that any other IP addresses/domains can send on your behalf and be accepted but mark them as insecure or spam. The other option is to use `+all`, although that is not recommended as it defeats the purpose of adding an SPF record, because it allows any other IP addresses/domains to send on your behalf |

This is how it looks at the DNS settings of a domain:

<!-- Image: spf.png -->

### How does this work?

An SPF record is configured as a TXT record in the DNS settings of your domain, which may include the IP address(es) or domain name(s) of all the authorised entities to send an email on your behalf. For all emails that are received by a mail server, they will query out for this SPF record and based on that information, an SPF authentication may pass or fail.

If the email originates from a server/IP address that is not mentioned in your SPF record, then the recipient server can reject your email or classify the email as spam. Depending on how the mail servers are configured, some emails can directly be rejected if there are no valid SPF records for your domain.

When you send an email, there are various “headers” (or additional information) that go along with your email. The recipient mail server looks for a “return-path” address in an email and checks the SPF records for the domain mentioned in this address [in some cases, the following headers are also looked at “mail from”, “bounce address”, “SPF address” or “envelope address”]. If the email was received from an address specified in this SPF record, then the SPF check passes & the email goes through. Otherwise, the SPF check fails and the email will be rejected or marked as spam.

```jsx
*** Message header from an email received in Proton Mail ***

Return-Path: <hello@zanil.me>
Authentication-Results: mail.protonmail.ch; spf=pass smtp.mailfrom=zanil.me
```

### Is SPF enough to protect my domain?

Short answer, No. 

One of the key challenges for SPF is with forwarded emails. Consider a scenario where you have configured SPF on your domains and you send an email to bob@acme.org. But Bob has set their emails to be forwarded to bob@me.com. In this case, your email would appear to be originating from “acme.org” which is not the case and hence would get impacted by the SPF policy.

Another issue is when the IP address mentioned in the SPF record changes before you can update the DNS record (in case of any mail server maintenance or updates) or if the email service provider is a global service that is used by others as well. In this case, someone else could try to spoof an email on your behalf.

To overcome these challenges, we can use DKIM to ensure that forwarded emails do not get rejected by the recipient mail server or get marked as spam. There is a simple UI that helps in generating an SPF record by answering a few questions. You can find it [here](https://www.spfwizard.net/).

- References
    
    https://www.spfwizard.net/
    
    https://redsift.com/guides/email-protocol-configuration-guide/all-you-need-to-know-about-spf-dkim-and-dmarc
    
    https://dmarcian.com/what-is-spf/
    
    https://www.cloudflare.com/en-gb/learning/dns/dns-records/dns-spf-record/
    

---

🔙 2️⃣ 🏠

---