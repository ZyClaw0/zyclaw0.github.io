---
title: "DMARC - Domain-based Message Authentication, Reporting and Conformance"
pubDatetime: 2025-01-17T00:00:00Z
modDatetime: 2025-01-17T00:00:00Z
featured: false
draft: false
tags:
  - "DNS"
  - "Email Security"
description: ""
---





We looked at SPF and DKIM as two email authentication protocols that help us improve our email security. DMARC builds on top of these protocols to prevent spam or phishing emails. With SPF and DKIM implemented, the domain owners did not have a way to know whether their outbound emails were processed correctly, i.e., whether these outbound emails were marked as spam or rejected by the recipient email server. There was no way to debug and find out more about these issues. DMARC helps address these with Reporting & Conformance.

Without DMARC, some recipient mail servers might reject or mark an email as spam if the SPF/DKIM authentication fails. DMARC provides precise instructions on what action the recipient mail servers should take with a non-conforming (non-compliant) email.

### Sample DMARC record

It is also a TXT record that goes into the DNS settings of your domain, with the Name field as `_dmarc`

`v=DMARC; p=quarantine; sp=reject; pct=; adkim=s; aspf=s; rua=mailto:aggregate_reports@yourdomain.com; ruf=mailto:failure_reports@yourdomain.com`

| v=DMARC | defines that this txt record contains a DMARC policy |
| --- | --- |
| p=quarantine | defines the policy for the domain, i.e., how should this email be treated |
| sp=reject | optional field, defines the policy for the subdomains |
| pct= | optional field, specifies the percentage of messages on which this policy has to be applied |
| adkim=s | optional field, defines the alignment mode for DKIM (s=strict / r=relaxed) |
| aspf=s | optional field, defines the alignment mode for SPF (s=strict / r=relaxed) |
| rua= | optional field, defines the reporting address for aggregate reports |
| ruf= | optional field, defines the reporting address for forensic reports |

Note: there are few more optional fields available & more on that [here](https://datatracker.ietf.org/doc/html/rfc#section-.).

### How does this work?

The `v` & `p` fields are the mandatory fields (& should be in that order) and make up the basic version of a DMARC policy. Upon receiving an email, the recipient mail server performs SPF/DKIM authentication checks. It is important to note that:

- DMARC passes if one or both of the SPF|DKIM checks are true
- DMARC fails if both SPF|DKIM checks fail

If successful, then the action defined in the policy p takes effect.

DMARC implementation is usually carried out in a phased manner, providing the administrator time to evolve from a relaxed control to a stricter control. The `p` can have the following values to support this:

- `none` this is the relaxed option, where DMARC enforcement doesn’t take effect. The outcome would depend on the recipient email server’s default behaviour for emails that fail SPF and DKIM.
- `quarantine` it is the midpoint where the recipient server can accept emails that fail SPF and DKIM but mark such emails (e.g. Spam or Junk email)
- `reject` it is the stricter option which rejects all inbound emails.

One can use any of these services to validate their DMARC deployment

[MX Toolbox](https://mxtoolbox.com/dmarc.aspx), [EasyDMARC](https://easydmarc.com/tools), [DMARCian](https://dmarcian.com/dmarc-inspector/), [PowerDMARC](https://powerdmarc.com/)

*Notes: In my testing:*

- *EasyDMARC could not identify DKIM records and was showing an incorrect DMARC result. Therefore, use this service with caution.*
    
    ![EasyDMARC.png](../../ZyRepo/DMARC%-%Domain-based%Message%Authentication,%Repor/EasyDMARC.png)
    
- *DMARCian was also unable to identify a DKIM record; nonetheless, the DMARC result was a pass.*
    
    ![DMARCian.png](../../ZyRepo/DMARC%-%Domain-based%Message%Authentication,%Repor/DMARCian.png)
    
    After setting up the DMARC records:
    
    ![DMARCian.png](../../ZyRepo/DMARC%-%Domain-based%Message%Authentication,%Repor/DMARCian.png)
    
    ![DMARCian.png](../../ZyRepo/DMARC%-%Domain-based%Message%Authentication,%Repor/DMARCian.png)
    
- *In the above cases, I suspect that these services are searching for a specific dkim selector used by popular services like Gmail, Yahoo or Microsoft. Since I am using a rd party email service provider, it is unable to identify the selector & hence fails the DKIM checks*.

### DMARC reports

The reporting option provides an added advantage to identify and track emails or sources that are trying to spoof you. This also helps while starting with the DMARC policy, allowing the administrator to adjust their configurations from a relaxed to a stricter control over time.

There are  reporting options:

- `rua` Reporting URL for Aggregate reports - usually these are sent to a third-party service that parses such emails and presents them in a graphical form. The summary of DMARC pass/failure is typically sent out with the results from the previous day.
- `ruf` Reporting URL for Forensic reports (or failure reports) - these are sent out immediately when an email fails a DMARC check, similar to an NDR (non-delivery report) or bounce email. However, configuring this to your email could be noisy depending on the number of failed DMARC checks, so be prepared!

### Is DMARC enough to protect my domain?

Short answer: not entirely, but to some degree.

DMARC doesn’t protect your domain from all kinds of email attacks; however, it is the best option to combat spoofing or phishing from the domain in your ownership. Look-alike domain attacks are still possible, and these techniques (SPF, DKIM and DMARC) don’t stop them, e.g. if the original domain is example.com and if the attacker spoofs an email from exampl.com.

As mentioned in the previous post, if the recipient mail server does not perform any of these authentication checks, then all fraud or spoofed emails could be delivered to the recipients without being subject to any filtering policies.

Since DMARC can pass if either of SPF|DKIM passes, this could potentially allow an attacker to craft a forged email from the same IP/domain as your email provider. In this case, the SPF check would pass. Therefore, the DMARC would also pass, delivering a spam email to the user. (however, this requires the attacker to be able to send an email originating from the same IP address/domain as your email service provider).

- References
    
    https://dmarc.org/
    
    https://www.cloudflare.com/en-gb/learning/dns/dns-records/dns-dmarc-record/
    
    https://www.maawg.org/activities/training/dmarc-training-series
    
    https://datatracker.ietf.org/doc/html/rfc
