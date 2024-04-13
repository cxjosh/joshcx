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

## what is `ESC1?`

esc1 is a specific vulnerability targeting overly permissive active directory certificate templates that are issued by a CA.

i was honestly pretty surprise how easy this was, and it's something that a lot of people don't seem to know about.

after managing to successfully escalate my normal domain account to a full on domain admin, i decided to spin up a CA and take a further look.
