---
title: Web LLM Attacks [PortSwigger]
description: My solutions to the portswigger labs on Web LLM Attacks
date: 2025-06-13 18:30:00 +0530
categories: [Portswigger]
tags: [llm]
---
# Exploiting LLM API's with excessive agency
> To solve the lab, use the LLM to delete the user `carlos`.

Well, i first go to the live chat option, and then talk to the chatbot. Usually these companies just use popular chatbots under the hood with wrapping your queries inside a custom prompt. So I just ask the chatbot what all things it can assist me with. It mentions that it can run raw SQL queries, so I decide to try my luck and write `select * from users`. Just like that it gives me the credentials for `carlos`.

![Chat](/assets/images/web-llm-attacks/image.png)

I then login as carlos and delete his account.

![Logged in as user carlos](/assets/images/web-llm-attacks/image-1.png)

Just press the delete account button. A popup will ask you to confirm the action, press yes. Lab solved !

![Solved](/assets/images/web-llm-attacks/image-2.png)

# Exploiting vulnerabilities in LLM APIs

# Indirect prompt injection

# Exploiting insecure output handling in LLMs
