AI HR Resume Screening

An AI-powered resume screening and recruitment automation workflow built with n8n as part of the Agentic AI & Automation Mastery program.

Overview

This workflow automates the initial candidate screening process by extracting resume data, analyzing the candidate against a target job description, assigning an AI-generated match score, and automatically handling candidate communication.

Workflow

Candidate Application
        ↓
      Webhook
        ↓
   Extract Resume
        ↓
  OpenAI GPT-4.1
        ↓
 AI Match Score & Analysis
        ↓
    Supabase
        ↓
   Score ≥ 60?
     ↙       ↘
  Selected   Rejected
     ↓          ↓
HR Email +   Rejection
Candidate     Email
Email

How It Works

1. Webhook receives candidate details and resume PDF.
2. Extract from File extracts text from the resume.
3. OpenAI GPT-4.1 analyzes the resume against the target job requirements and generates a match score, skills, and reasoning.
4. Supabase stores candidate information and screening results.
5. An IF condition checks whether the match score is 60 or above.
6. Selected candidates trigger HR notification, resume summary generation, database status update, and a shortlist email.
7. Rejected candidates receive an automated and professional rejection email.

Tech Stack

* n8n — Workflow automation
* OpenAI GPT-4.1 / GPT-4.1 Mini — Resume analysis & email generation
* Supabase — Candidate data & status management
* Gmail — Automated candidate & HR communication
* Webhook — Application intake

Key Skills

AI Resume Screening • Prompt Engineering • Workflow Automation • Conditional Logic • PDF Processing • Database Integration • Automated Recruitment Communication
