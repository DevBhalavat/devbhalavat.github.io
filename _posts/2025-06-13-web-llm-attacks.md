---
title: Web LLM Attacks (PortSwigger)
description: My solutions to the portswigger labs on Web LLM Attacks
author: Dev Bhalavat
date: 2025-06-13 17:00:00 +0530
categories: [Portswigger]
tags: [llm]
---

# Exploiting LLM APIs with Excessive Agency

> **Objective:** Delete the user `carlos` to solve the lab.

## Approach

I started by interacting with the application's **Live Chat** feature, which was powered by a Large Language Model (LLM) API. It's common for such chatbots to wrap user inputs within predefined prompts, often exposing more functionality than intended.

To explore the chatbot's capabilities, asked it a question regarding its capabilities. Surprisingly, the bot revealed that it had the ability to execute raw SQL queries.

## Exploitation

To test this, I submitted the following SQL query to the chatbot:

```sql
SELECT * FROM users;
```

The bot responded with data of the `carlos` account. 

![Chat output showing SQL query result](/assets/images/web-llm-attacks/image.png)

Using the retrieved credentials, I logged in as `carlos`.

![Logged in as user carlos](/assets/images/web-llm-attacks/image-1.png)

Once logged in, I navigated to the account settings and clicked the **Delete Account** button. A confirmation popup appeared; upon accepting, the account was successfully deleted.

![Lab solved after deleting user](/assets/images/web-llm-attacks/image-2.png)

---

✅ Lab Solved

# Exploiting vulnerabilities in LLM APIs

# Indirect prompt injection

# Exploiting insecure output handling in LLMs
