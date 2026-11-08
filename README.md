# 🤖 Telegram AI Chatbot with n8n

An AI-powered Telegram chatbot built using **n8n**, an LLM, and conversational memory to create an interactive chat experience.

This project is one of my first practical experiments in AI Automation, exploring how workflow automation, Large Language Models (LLMs), and memory can work together to build conversational AI applications.

## 📌 Project Overview

The workflow connects Telegram with an AI model to receive user messages, process them, maintain conversational context, and generate responses automatically.

It demonstrates the fundamentals of building AI-powered automation workflows using a visual automation platform.

## ⚙️ Technologies Used

- **n8n** – Workflow automation and orchestration.
- **Telegram Bot API** – Receiving and sending messages.
- **LLM** – Understanding user messages and generating responses.
- **Conversational Memory** – Maintaining context across messages.

## 🔄 How It Works

The workflow follows these steps:

1. **Telegram Trigger:** Listens for incoming messages from the Telegram bot.
2. **AI Processing:** Sends the user's message to the connected language model.
3. **Memory:** Maintains conversational context to support follow-up questions.
4. **Telegram Response:** Sends the generated response back to the user.

## 🏗️ Workflow Architecture

```text
Telegram User
      |
      v
Telegram Trigger
      |
      v
AI Processing
      |
      +------ Conversational Memory
      |
      v
LLM Response
      |
      v
Telegram Message
```

 Workflow Preview

Add a screenshot of your n8n workflow here.

```text
assets/workflow-screenshot.png
```

Getting Started

 Prerequisites

- An active n8n instance.
- A Telegram account.
- A Telegram Bot created using BotFather.
- API credentials for your chosen LLM provider.

### Setup Instructions

1. Clone this repository:

```bash
git clone https://github.com/YOUR_USERNAME/n8n-telegram-ai-chatbot.git
```

2. Open your n8n instance.

3. Import the `workflow.json` file into n8n.

4. Configure your Telegram Bot credentials.

5. Connect your LLM credentials and configure the memory component.

6. Activate the workflow and start chatting with your Telegram bot.

## 🔐 Security

- Never upload API keys, bot tokens, or private credentials.
- Use n8n credentials management for sensitive information.
- Keep your `.env` files and private configuration out of version control.

## 🎯 What I Learned

Through this project, I explored:

- Building automated workflows using n8n.
- Integrating Telegram with AI-powered applications.
- Connecting LLMs to automated workflows.
- Understanding conversational memory and context management.
- Designing simple AI-powered chat applications.

 Future Improvements

Some planned enhancements include:

- Adding external tools and API integrations.
- Improving conversation memory.
- Adding error handling and fallback mechanisms.
- Exploring more advanced AI Agent capabilities.
- Integrating a knowledge base for context-aware responses.

 Author

**Nour Elsanafawy**

Aspiring Agentic AI & Automation Developer, focused on building intelligent AI-powered systems and practical automation solutions.

- LinkedIn: [Connect with me](https://www.linkedin.com/in/nour-hassan-elsanafawy-5a6251299)
- GitHub: [NaNa557](https://github.com/NaNa557)

---

⭐ If you find this project interesting, feel free to explore the repository!

*Built as part of my journey into AI Automation and Agentic AI Engineering.*
