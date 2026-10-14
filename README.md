# RentVoice

[![License: All rights reserved](https://img.shields.io/badge/License-All_rights_reserved-555.svg)](./LICENSE)
[![Live Demo](https://img.shields.io/badge/Live_Demo-Open-0a7.svg)](https://rentvoice.twinstackstudio.com)

**Voice AI & automation**

An AI voice agent for a rental company. Ava answers renter calls by phone or from a button on the website, searches the listings, checks whether the caller fits, books a viewing and saves the lead. Every call lands in a dashboard.

[**Open the live demo**](https://rentvoice.twinstackstudio.com) · [**Work with TwinStack Studio**](https://twinstackstudio.com/contact)

![RentVoice diagram: a caller speaks to Vapi, Vapi calls n8n workflows, and n8n reads and writes PostgreSQL and sends follow-ups by email, SMS and Slack.](./assets/rentvoice-howitworks.png)

> **Note:** HarborKey Rentals and its listings are fictional; the demo is not connected to a real property manager. Speech, the language model and the voice run on Vapi's cloud, so each call has a small running cost.

## What it does

- Vapi runs the conversation: speech-to-text, GPT-4.1 mini and a natural voice
- Every action Ava takes is an n8n workflow, so the business logic stays visible and easy to change
- Searches listings, answers questions about a property, checks open viewing slots and books one
- Qualifies each caller and saves the lead to PostgreSQL
- Each call is stored with its recording, transcript, AI summary, extracted details and cost
- Talk to Ava straight from the browser, no phone needed

## Screenshots

| Homes | Leasing console |
| --- | --- |
| ![Homes](./assets/rentvoice-1.png) | ![Leasing console](./assets/rentvoice-2.png) |

| How it works | Home page |
| --- | --- |
| ![How it works](./assets/rentvoice-3.png) | ![Home page](./assets/rentvoice-4.png) |


## Technology

| Layer | Stack |
| --- | --- |
| Voice AI | Vapi, Deepgram, GPT-4.1 mini |
| Automation | n8n, Webhooks |
| Backend | PostgreSQL, Python |
| Frontend | React, Vite, Tailwind CSS |

## Architecture

```mermaid
flowchart LR
  CALL[Caller] -->|phone / web call| VAPI[Vapi voice agent<br/>Deepgram · GPT-4.1 mini]
  VAPI -->|tool calls| WH[Webhook proxy]
  WH --> N8N[n8n workflows<br/>search homes · book viewings · follow-up]
  N8N --> PG[(PostgreSQL<br/>listings · leads · viewings · calls)]
  PG --> UI[React site + leasing console<br/>recordings · transcripts]
```

## Source code

This is the public showcase. The source code is kept in a private repository. Try the live demo above, and [contact TwinStack Studio](https://twinstackstudio.com/contact) for a walkthrough or a similar project.

## Built by TwinStack Studio

TwinStack Studio builds full-stack websites, web applications, mobile apps,
dashboards, portals, automation, and AI-powered products.

[GitHub](https://github.com/twinstack-studio) ·
[Website](https://twinstackstudio.com) ·
[Email](mailto:hello@twinstackstudio.com)

© 2026 TwinStack Studio. All rights reserved. See [LICENSE](./LICENSE).
