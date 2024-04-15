---
date: 2024-04-13
title: esc1 - a surprisingly easy privilege escalation
type:
- post
- posts
weight: 10
series:
aliases:
- /blog/adcs/
---

## what is adcs?

adcs - active directory certificate services is a windows server role that issues and manages PKI certificates that are used in authentication and communication protocols.

these certificates are issued through root and subordinate CA's to various different users, computers and services to maintain certificate validity.

## what is esc1?

esc1 is a specific vulnerability targeting overly permissive active directory certificate templates that are issued by these CA's.

more specifically, if a template allows a standard domain user or domain computer to enroll/request a template, depending on how the template is configured they have the potential to impersonate any user on the domain.

i was pretty surprised how easy this was and even more so by the fact that i haven't come across it before.

the first thing i tried after coming across it was to attempt to replicate this vulnerability at my current workplace's AD environment. after approximately an hour using only a standard domain user account, i had successfully manage to impersonate the head of the SOC team to create a new domain user account and add it to the domain admins group using LDAP queries.

![joshPwnedYou](/joshPwnedYou.png)


## what makes a template vulnerable?

there are a few things that we are looking for when exploiting ESC1, however the most damning are enrolment rights being granted to low privileged users and requesters being able to specify a subjectAltName in the CSR.

**example 1:**

![subjectAltName](/sanRequest.png)

in the above image the ability to include a subjectAltName in the CSR to that specific template is allowed.

active directory will prioritise the SAN name in a certificate for identity if the field is present. this means that by specifying a specific username in the SAN a .pfx can be requested to impersonate any user (e.g domain administrators)

when creating a new template it does give a warning mentioning the risks upon allowing anybody to request a SAN, however if cloning an existing template with it enabled it does not grant a warning.

ฅ^•ﻌ•^ฅ

### proof of concept

the tool that i used for absolutely everything was certipy which can be downloaded from the below link:

https://github.com/ly4k/Certipy

credit to ly4k for maintaining such a fantastic tool.

for the purpose of this blog i have spun up 2 VM's, one of which mimics an AD & CA server (CXLABS-DC-01), and the other being a standard on domain laptop (CXLABS-VM).

i've created a template under the name of VulnTemplate which allows for both the requestee to specify the SAN, in addition to normal domain users being able to enroll into this template.

 > python3 entry.py find -u "joshua@CXLABS.LOCAL" -p "REDACTED" -dc-ip "192.168.197.129" -stdout -scheme ldap

 using the find module of certipy to enumerate all ADCS templates, where -u and -p are the credentials for the domain account and the DC-IP is the CA.

 it's important to note that certipy uses LDAPS by default, so if spinning up a quick lab and not wanting to issue a cert for LDAPS, you can use "-scheme ldap" to explicitly use port 386.

 output from command:

 ![VulnTemplate](/VulnTemplate.png)
