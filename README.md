# WhatsApp ChatBot with n8n and Google Gemini

A WhatsApp chatbot built using n8n workflow automation and Google Gemini AI for natural language processing.

## Overview

This project implements a WhatsApp chatbot that:
- Receives incoming WhatsApp messages via webhook
- Processes messages using Google Gemini AI
- Maintains conversation context with memory buffer
- Sends responses back via Twilio API

## Prerequisites

Before using this workflow, you'll need:

1. **n8n instance** (self-hosted or cloud)
2. **Twilio Account** with WhatsApp sandbox configured
3. **Google Gemini API Key** (formerly PaLM API)
4. **WhatsApp Business Account** or access to Twilio WhatsApp sandbox

## Workflow Components

The workflow consists of the following nodes:

1. **Webhook Node**: Receives incoming WhatsApp messages
2. **Edit Fields Node**: Extracts message content and sender info
3. **AI Agent Node**: Orchestrates the conversation flow
4. **Google Gemini Chat Model**: Provides AI responses
5. **Simple Memory Node**: Maintains conversation context
6. **Edit Fields1 Node**: Formats the response
7. **HTTP Request Node**: Sends response via Twilio API

## Setup Instructions

### 1. Configure Twilio WhatsApp Sandbox

1. Set up a Twilio account
2. Configure WhatsApp sandbox
3. Note your Twilio Account SID and Auth Token

### 2. Set Up Google Gemini API

1. Get API key from Google AI Studio
2. Create credentials in n8n for Google Gemini

### 3. Import Workflow

1. Import the provided JSON workflow into your n8n instance
2. Update the following credentials:
   - Twilio HTTP Basic Auth (Account SID as username, Auth Token as password)
   - Google Gemini API key

### 4. Configure Webhook

1. Note your n8n webhook URL
2. Configure Twilio to send WhatsApp messages to this URL

## Environment Variables

Ensure these environment variables are set in your n8n instance:

![Work Flow](https://github.com/user-attachments/assets/32f3c4ef-7dc1-43cf-a89e-b120015d1293)

