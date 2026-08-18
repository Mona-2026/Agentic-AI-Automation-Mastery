AI Customer Feedback & Sentiment Agent

An AI-powered customer feedback automation workflow built with n8n that analyzes reviews, detects sentiment and churn risk, and automatically responds or escalates based on the customer’s feedback.

Overview

This workflow validates customer feedback, uses OpenAI GPT-4.1 Mini to translate and analyze reviews, calculates churn risk, routes feedback based on sentiment, sends personalized emails, and stores the analysis in Supabase.

Workflow

Customer Feedback → Webhook → Input Validation → AI Sentiment Analysis → Sentiment Classification → Automated Response / Escalation → Supabase

How It Works

1. Webhook receives customer email, booking ID, and feedback.
2. IF node validates the required information.
3. OpenAI GPT-4.1 Mini detects language, translates the feedback, identifies sentiment, calculates churn risk, and extracts complaints.
4. Switch routes the feedback into Extremely Angry, Neutral, or Delighted paths.
5. Gmail sends an urgent escalation for high-risk complaints, an acknowledgement for neutral feedback, or a thank-you offer for positive feedback.
6. Supabase stores the complete feedback and AI analysis.

Tech Stack

* n8n — Workflow automation
* OpenAI GPT-4.1 Mini — Sentiment & churn analysis
* Supabase — Feedback database
* Gmail — Automated customer communication
* Webhook — Feedback intake

Key Skills

Sentiment Analysis • Customer Experience Automation • Churn Risk Detection • AI Text Classification • Multilingual Processing • Conditional Logic • Database Integration • Automated Email Responses
