Nexium AI — AI-Powered CV Tailoring & Interview Preparation

Overview

Nexium AI is an AI-powered career automation system built to help candidates improve their CVs and prepare for job interviews.

The system takes a candidate’s CV, target Job Description (JD), and selected service, then automatically processes the information using AI.

Nexium AI currently provides two main services:

* CV Tailoring & ATS Optimization
* AI Interview Preparation

The complete process is automated using n8n, from receiving the CV to generating and delivering the final report.

How It Works

The workflow starts with an n8n Webhook that receives the candidate’s information, target job description, selected service, and CV as a Base64-encoded PDF.

The CV is decoded and processed to extract its text.

Custom JavaScript logic then cleans and organizes the candidate’s information, including the candidate’s name, email, CV content, job description, and selected service.

A Switch node checks the selected service and sends the request to the correct AI workflow.

The AI analyzes the information and generates a personalized result.

The result is then converted into an HTML report, sent to the candidate through Gmail, and saved in Supabase.

CV Tailoring & ATS Optimization

The CV Tailoring branch uses OpenAI GPT-4o-mini to compare the candidate’s CV with the target job description.

The AI generates:

* ATS Match Score
* Missing Keywords
* Tailored CV Bullet Points
* Professional Summary

The tailored bullet points are rewritten using strong action verbs while keeping the candidate’s existing experience in focus.

The final result is converted into a professional ATS optimization report and automatically sent to the candidate through Gmail.

The report is also saved in Supabase for record keeping.

AI Interview Preparation

The Interview Preparation branch uses OpenAI GPT-4o-mini to create interview preparation based on the candidate’s CV and target job description.

The AI generates:

* Technical Questions
* Behavioral Questions
* Situational Questions
* Scoring Rubric

This makes the preparation specific to the candidate and the job they are applying for instead of providing only generic interview questions.

The completed interview preparation report is automatically sent to the candidate through Gmail and stored in Supabase.

Workflow Architecture

The complete workflow follows this process:

CV Submission → Base64 Decoding → PDF Text Extraction → Data Processing → Service Selection → AI Analysis → Report Generation → Email Delivery → Database Storage

This structure allows multiple career services to work through a single automated workflow.

AI Processing

Nexium AI uses OpenAI GPT-4o-mini for its AI-powered features.

For CV Tailoring, the AI focuses on CV-to-JD matching, ATS optimization, missing keywords, improved bullet points, and candidate summarization.

For Interview Preparation, the AI focuses on generating technical, behavioral, and situational questions based on the candidate’s CV and target role.

Both AI workflows use structured JSON output so that the results can be processed reliably by the automation.

Automated Report Generation

After the AI generates the results, custom JavaScript logic converts the output into a clean HTML report.

The CV Tailoring report includes the ATS score, missing keywords, tailored bullet points, and summary.

The Interview Preparation report includes technical, behavioral, and situational questions along with the scoring rubric.

This allows the candidate to receive a ready-to-use report instead of raw AI output.

Email Delivery

The generated reports are automatically delivered through Gmail.

Each report is personalized with the candidate’s information and contains the complete AI-generated results.

This removes the need to manually prepare and send career reports.

Database Storage

Supabase is used to store the generated reports.

CV Tailoring reports are stored in the cv_tailoring_records table.

Interview Preparation reports are stored in the interview_sessions table.

This provides a structured record of the generated results and can support future features such as candidate history and analytics.

Data Processing

Custom JavaScript nodes are used to prepare and validate the incoming data.

The workflow can handle different input field names for candidate information and job descriptions.

It also includes fallback logic to find the candidate’s email and name from the CV when the information is not directly available in the request.

The CV is processed directly from the uploaded PDF, so candidates do not need to manually copy and paste their CV content.

Tech Stack

n8n — Workflow automation and process orchestration

OpenAI GPT-4o-mini — AI-powered CV analysis and interview preparation

Supabase — Storage for generated reports and interview sessions

Gmail — Automated email delivery

JavaScript — Data processing, validation, JSON parsing, and report generation

PDF Processing — Extraction of CV content from uploaded PDF files

Key Features

Nexium AI combines AI and automation to create a simple career assistance system.

The workflow can:

* Process CVs automatically
* Compare CVs with target job descriptions
* Calculate an ATS match score
* Find missing job-related keywords
* Improve CV bullet points
* Generate personalized interview questions
* Create professional career reports
* Send reports automatically through email
* Store generated results in Supabase
* Support multiple services through one workflow

Use Cases

Nexium AI can help candidates:

* Improve their CV for a specific job
* Understand how well their CV matches a job description
* Find important keywords missing from their CV
* Improve their existing CV bullet points
* Prepare for technical interviews
* Practice behavioral interview questions
* Prepare for situational interview questions
* Receive personalized career guidance automatically

Future Improvements

The workflow can be extended with additional career services such as:

* AI Mock Interviews
* Cover Letter Generation
* LinkedIn Profile Optimization
* Job Recommendations
* Skill Gap Analysis
* Resume Benchmarking
* Automated Job Application Tracking

Conclusion

Nexium AI shows how AI and workflow automation can be used to solve real-world career problems.

Instead of manually reviewing CVs, finding missing keywords, preparing interview questions, creating reports, and sending emails, the complete process is automated.

The system brings together CV processing, AI analysis, personalized recommendations, automated email delivery, and database storage into one simple workflow.
