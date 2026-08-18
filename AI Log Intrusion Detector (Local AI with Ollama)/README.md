AI-Powered Intrusion Detection & Alerting Agent

An AI-powered security monitoring workflow built with n8n that analyzes server logs, detects potential threats, classifies their severity, stores security events, and sends real-time alerts.

Overview

This workflow automates intrusion detection by filtering suspicious logs, using Llama 3 to analyze potential attacks, classifying threats by severity, logging them in Supabase, and sending critical security alerts via Gmail.

Workflow

Server Log → Webhook → Suspicious Log Filter → AI Threat Analysis → JSON Parser → Threat Severity Classification → Supabase Threat Log → Security Alert

How It Works

1. Webhook receives server log data.
2. IF node filters logs containing suspicious patterns.
3. Ollama + Llama 3 analyzes the log for attacks such as Brute Force, SQL Injection, XSS, Path Traversal, and Port Scanning.
4. JavaScript validates and structures the AI response.
5. Switch classifies the threat as Critical, Medium, or Low.
6. Gmail sends an immediate alert for Critical threats.
7. Supabase stores the complete security event.
8. Gmail sends a final SOC notification with the threat details and recommended action.

Tech Stack

* n8n — Workflow automation
* Ollama / Llama 3 — Local AI threat analysis
* Supabase — Security event logging
* Gmail — Automated threat alerts
* JavaScript — JSON validation & processing
* Webhook — Real-time log ingestion

Key Skills

AI Security Analysis • Threat Detection • Log Monitoring • Security Automation • Conditional Logic • Local LLMs • JSON Processing • Database Integration • Automated Alerting
