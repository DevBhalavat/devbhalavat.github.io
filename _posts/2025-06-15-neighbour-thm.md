---
title: Neighbour [Try Hack Me]
description: My writeup for the Neighbour box on TryHackMe.
date: 2025-06-15 21:30:00 +0530
categories: [Try Hack Me]
tags: [web exploitation, beginner, url manipulation, ctf walkthrough, nmap]
image: /assets/images/neighbour-tryhackme/title.png
---
A quick and easy box — solved in under a minute.

I started with an `nmap` scan, which revealed two open ports: **22 (SSH)** and **80 (HTTP)**.  
![NMAP](/assets/images/neighbour-tryhackme/nmap.png)

Navigating to the web server on port 80, I was greeted with a simple login portal.  
![Webpage](/assets/images/neighbour-tryhackme/login.png)

With no credentials at hand, I viewed the page source (`Ctrl+U`) to look for any hints.  
![Source Code](/assets/images/neighbour-tryhackme/source.png)

The source contained hardcoded credentials: `guest:guest`, and also hinted at the presence of an `admin` account.

I logged in as guest.  
![Landing](/assets/images/neighbour-tryhackme/guest.png)

Once logged in, I noticed the URL structure:  
`http://<ip>/profile.php?user=guest`

Since the username was passed as a GET parameter, I simply changed `guest` to `admin` — and that was it. The flag was revealed.  
![Admin](/assets/images/neighbour-tryhackme/admin.png)