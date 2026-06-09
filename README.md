# 📅 n8n AI Agent Day Planner

An intelligent AI-powered day planning assistant built with n8n that leverages multiple integrations to help you manage your schedule, send communications, and stay organized.

## 🎯 Overview

The **AI Agent Day Planner** is an automated workflow that uses artificial intelligence to assist users with schedule management. It integrates with multiple services to provide a comprehensive planning and communication solution, including calendar management, email notifications, and messaging capabilities.

## ✨ Features

- **🤖 AI Agent Assistant**: Powered by OpenAI's GPT-4o-mini model for intelligent conversations and scheduling assistance
- **📱 Chat Interface**: Real-time chat trigger for user interaction
- **📅 Google Calendar Integration**: Retrieve and manage calendar events
- **📧 Gmail Integration**: Send email notifications and reminders
- **💬 Telegram Support**: Send text messages via Telegram for quick notifications
- **🔍 Web Search**: SerpAPI integration for information lookup
- **🧠 Conversation Memory**: Maintains context using a sliding window memory buffer

## 🛠️ Technology Stack

- **n8n**: Workflow automation platform
- **OpenAI GPT-4o-mini**: AI language model for intelligent responses
- **Google Calendar API**: Calendar event management
- **Gmail API**: Email service integration
- **Telegram Bot API**: Messaging service
- **SerpAPI**: Web search functionality

## 📋 Workflow Components

### Nodes

1. **When chat message received** - Triggers the workflow on incoming chat messages
2. **AI Agent** - Core intelligent agent that orchestrates all actions
3. **OpenAI Chat Model** - LLM provider for AI responses
4. **Simple Memory** - Maintains conversation context (buffer window memory)
5. **Get many events in Google Calendar** - Retrieves calendar events
6. **Send a message in Gmail** - Sends email notifications
7. **Send a text message in Telegram** - Sends Telegram messages
8. **SerpAPI** - Performs web searches

### System Prompt

The AI Agent is configured with a context-aware system message that:
- Identifies itself as a schedule management assistant
- Displays current date and time dynamically
- Helps users manage their daily schedule effectively

## 🚀 Getting Started

### Prerequisites

- n8n instance (self-hosted or cloud)
- OpenAI API key
- Google Calendar API credentials
- Gmail API credentials
- Telegram Bot token
- SerpAPI key

### Installation

1. **Import the Workflow**: 
   - Open n8n and import the `AI Agent - Day Planner.json` file
   
2. **Configure Credentials**:
   - Add your OpenAI API credentials
   - Connect your Google Calendar account
   - Set up Gmail integration
   - Configure Telegram bot token
   - Add SerpAPI key

3. **Enable the Workflow**:
   - Toggle the workflow active status to start using it

4. **Deploy**: 
   - Deploy to your n8n instance (cloud or self-hosted)

## 💡 Use Cases

- **Schedule Management**: Ask the AI to check your calendar and manage events
- **Meeting Reminders**: Get email and Telegram notifications about upcoming events
- **Quick Information**: Use web search to find information and schedule it
- **Communication**: Send emails and messages directly through the chat interface
- **Context-Aware Planning**: The AI maintains conversation history for better understanding of your needs

## 📊 Workflow Architecture

```
Chat Message Input
       ↓
   AI Agent (with context)
       ↙      ↓      ↘
    Gmail  Calendar  Telegram
       ↓      ↓      ↘
      (Tools available for AI to use)
       ↓
   Chat Response
```

## ⚙️ Configuration

### System Message Customization

You can modify the system prompt in the **AI Agent** node to change the assistant's behavior:

```
You are assisting the user with managing their schedule.
Today is {{ $now.format('dddd, MMMM D, YYYY') }} and the current time is {{ $now.format('h:mm A') }}.
```

### Memory Settings

The workflow uses a **Simple Memory** node with a sliding window buffer that maintains recent conversation context. Adjust the memory settings as needed.

## 🔗 API Integrations

| Service | Purpose | Required |
|---------|---------|----------|
| OpenAI | AI responses | ✅ Yes |
| Google Calendar | Event management | ✅ Yes |
| Gmail | Email sending | ✅ Yes |
| Telegram | Messaging | ❌ Optional |
| SerpAPI | Web search | ❌ Optional |

## 📝 Example Interactions

- "What's on my calendar for today?"
- "Send an email to my team about the meeting"
- "Remind me about my appointment via Telegram"
- "Search for information about JavaScript frameworks"
- "Add a note about tomorrow's plans"

## 🐛 Troubleshooting

- **Workflow not triggering**: Ensure the chat trigger is properly configured with a valid webhook ID
- **Calendar not showing events**: Verify Google Calendar API credentials and calendar selection
- **Messages not sending**: Check that Gmail and Telegram credentials are correctly configured
- **AI not responding**: Verify OpenAI API key is valid and has sufficient credits

