# 🤖 Telegram AI Chatbot with n8n

A Telegram chatbot built in **n8n** that uses **Google Gemini** to answer messages and remembers the last 10 messages of each user's conversation.

This is my first hands-on AI automation project. I built it to understand how a trigger, an AI Agent node, a chat model, and memory connect inside an n8n workflow.

![Workflow screenshot](assets/workflow-screenshot.png)

## What It Does

- Receives text messages sent to a Telegram bot.
- Passes each message to an AI Agent powered by Google Gemini (Flash-Lite).
- Keeps a separate conversation memory per Telegram user, so follow-up questions work and users never see each other's context.
- Sends the AI's answer back to the chat.

## Tech Stack

| Component | Used for |
|---|---|
| **n8n** | Workflow orchestration |
| **Telegram Bot API** | Receiving and sending messages |
| **Google Gemini (Flash-Lite)** | Language model behind the agent |
| **n8n AI Agent node** | Connects the model and memory |
| **Simple Memory (Window Buffer)** | Short-term conversation context |

## How It Works

```
Telegram message
      │
      ▼
Telegram Trigger
      │
      ▼
AI Agent  ◄── Google Gemini Chat Model
      ▲
      └────── Simple Memory (keyed by Telegram user ID, last 10 messages)
      │
      ▼
Send a text message (Telegram)
```

1. **Telegram Trigger** fires when a user messages the bot.
2. **AI Agent** takes the message text as its input.
3. **Google Gemini Chat Model** generates the reply.
4. **Simple Memory** uses the sender's Telegram user ID as the session key, so each user has their own context window of 10 messages.
5. **Send a text message** returns the agent's output to the user.

## Getting Started

### Prerequisites

- An n8n instance (cloud or self-hosted)
- A Telegram bot token from [@BotFather](https://t.me/BotFather)
- A Google Gemini API key from [Google AI Studio](https://aistudio.google.com/)

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/NaNa557/n8n-telegram-ai-chatbot.git
   ```
2. In n8n, go to **Workflows → Import from file** and select `first_n8n.json`.
3. Create your own credentials for **Telegram** and **Google Gemini** and attach them to the matching nodes.
4. In the **Send a text message** node, make sure the chat ID comes from the incoming message (not a fixed value).
5. Activate the workflow and send a message to your bot.

> **Security note:** The exported workflow contains no tokens or API keys. Credentials are stored in n8n's credential manager and are never committed to this repo.

## Current Limitations

- **Text only.** Photos, voice notes, and stickers are not handled yet.
- **Memory is temporary.** Simple Memory is held in n8n's memory, so it resets when n8n restarts.
- **No tools yet.** The agent answers from the model alone and cannot look anything up or take actions.

## What I Learned

- How the AI Agent node connects to a chat model and a memory sub-node.
- Why memory needs a session key: using the Telegram user ID keeps each user's conversation separate.
- How to keep credentials out of exported workflows and out of Git.

## Next Steps

- [ ] Add a system prompt to give the agent a clear role and tone
- [ ] Add a tool (Google Sheets or an HTTP request) so the agent can work with real data
- [ ] Handle non-text messages with a fallback reply
- [ ] Move to persistent memory (database-backed)
- [ ] Add basic error handling

## Author

**Nour Elsanafawy** — Agentic AI Engineer | AI Automation | LLMs | AI Agents
Frontend developer moving into AI automation and agentic systems.

- LinkedIn: [nour-hassan-elsanafawy](https://www.linkedin.com/in/nour-hassan-elsanafawy-5a6251299)
- GitHub: [NaNa557](https://github.com/NaNa557)
