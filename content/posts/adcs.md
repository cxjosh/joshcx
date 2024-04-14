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

i was pretty surprised how easy this was and even more so by the fact that i haven't come across it before.

the first thing i tried after coming across it was to replicate this vulnerability at my current workplace's environment. after approximately an hour using only a domain user account, i had successfully manage to impersonate the head of the soc team to create a new domain user account and it to the domain admins group using LDAP queries.

after managing to successfully escalate my normal domain account privileges to full domain admin at the company i work for, i decided to spin up a CA and take a further look.

## what makes a template vulnerable?

there are a few things that we are looking for when exploiting ESC1, however the most damning are enrolment rights being granted to low privileged users and requesters being able to specify a subjectAltName in the CSR.

**example 1:**

![subjectAltName](/sanRequest.png)

in the above image the ability to include a subjectAltName in the CSR to that specific template is allowed.

active directory will prioritise the SAN name in a certificate for identity if the field is present. this means that by specifying a specific username in the SAN a .pfx can be requested to impersonate any user (e.g domain administrators)

when creating a new template it does give a warning mentioning the risks upon allowing anybody to request a SAN, however if cloning an existing template with it enabled it does not grant a warning.

$ this is a command
>another command test
