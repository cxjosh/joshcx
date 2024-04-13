---
date: 2024-04-13
title: esc1 - a concerningly easy privilege escalation
type:
- post
- posts
weight: 10
series:
aliases:
- /blog/adcs/
---

## what is esc1?

esc1 is a specific vulnerability targeting overly permissive active directory certificate templates that are issued by a CA.

i was honestly pretty surprise how easy this was, and it's something that a lot of people don't seem to know about.

after managing to successfully escalate my normal domain account to a full domain admin account at the company i work for, i decided to spin up a CA and take a further look.

## what makes a template misconfigured?

there are a few things that we are looking for when exploiting ESC1, however the most damning are enrolment rights being granted to low privileged users and requesters being able to specify a subjectAltName in the CSR.

![static](images/meow.jpg)
