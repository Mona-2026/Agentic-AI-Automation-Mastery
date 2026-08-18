AI Invoice Processing Agent

An AI-powered invoice processing and validation workflow built with n8n as part of the Agentic AI & Automation Mastery program.

Overview

This workflow automates invoice processing by extracting invoice data from PDFs, using AI to structure the information, detecting duplicate invoices, flagging high-value invoices for approval, and storing processed records.

Workflow

The workflow follows an automated invoice processing pipeline:

1. Invoice Submission — Receives the invoice PDF through a webhook.
2. Data Extraction — Extracts text and relevant information from the invoice PDF.
3. AI Processing — OpenAI GPT-4.1 Mini structures the invoice details such as vendor name, invoice number, amount, due date, and email.
4. Duplicate Detection — Checks Supabase for existing invoices with the same vendor and invoice number.
5. Duplicate Handling — Duplicate invoices trigger an automated alert and processing is halted.
6. Approval Check — Invoices above $5,000 are flagged for manual approval.
7. Data Storage — Valid invoices are stored in Supabase and Google Sheets.
8. Confirmation — Gmail automatically sends a confirmation email to the vendor after successful processing.

Tech Stack

* n8n — Workflow automation
* OpenAI GPT-4.1 Mini — AI invoice data extraction
* Supabase — Invoice database & duplicate detection
* Google Sheets — Invoice record management
* Gmail — Automated notifications
* Webhook & PDF Extraction — Invoice intake and processing

Key Skills

AI Document Processing • Prompt Engineering • Workflow Automation • Duplicate Detection • Conditional Logic • Database Integration • Document Extraction • Automated Notifications
