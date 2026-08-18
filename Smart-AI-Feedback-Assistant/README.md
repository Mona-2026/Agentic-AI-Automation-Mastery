Smart AI Feedback Assistant

An AI-powered feedback automation workflow built with n8n as part of the Agentic AI & Automation Mastery program.

Overview

This workflow automates the process of collecting customer feedback, storing it, generating a personalized AI response, and sending it back to the customer via email.

Workflow

Customer Feedback
       ↓
    Webhook
       ↓
    Supabase
       ↓
  OpenAI GPT-4.1
       ↓
     Gmail

How It Works

1. Webhook receives customer name, email, feedback, and rating.
2. Supabase stores the submitted feedback.
3. OpenAI GPT-4.1 analyzes the feedback and generates a professional response based on the rating and sentiment.
4. Gmail automatically sends the personalized response to the customer.

Tech Stack

* n8n — Workflow automation
* OpenAI GPT-4.1 — AI response generation
* Supabase — Data storage
* Gmail — Automated email delivery
* Webhook — Feedback collection

Key Skills

AI Integration • Prompt Engineering • Workflow Automation • API Integration • Database Integration • Automated Communication
