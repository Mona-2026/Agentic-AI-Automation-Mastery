🚀 LeadScoutAI — Automated Lead Generation & Cold Outreach System

An AI-powered lead generation and cold outreach workflow built with n8n. It automatically finds potential business leads, extracts public contact emails, generates personalized cold emails using AI, sends the emails through Gmail, and tracks the outreach activity in Google Sheets.

The goal of this workflow is to automate the repetitive parts of lead research and B2B outreach while keeping the process organized and personalized.

🎯 What This Workflow Does

The workflow starts when a user provides basic information such as the business type, target location, and number of leads required.

It then automatically:

* Searches for relevant local businesses
* Collects business information and websites
* Filters businesses with valid websites
* Uses Google Gemini to find public business email addresses
* Checks whether a valid email was found
* Saves valid leads in Google Sheets
* Uses OpenAI to write personalized cold emails
* Sends the emails through Gmail
* Updates the lead status after sending
* Records the sending time
* Adds a short delay before processing the next lead

This turns the complete lead-generation and outreach process into an automated workflow.

⚙️ How the Workflow Works

1. Webhook Trigger

The workflow starts with an n8n Webhook that receives the user’s lead-generation request.

The input can include:

* Business type
* Target location
* Lead limit

For example:

Find 10 restaurants in Karachi.

The workflow uses this information to begin searching for relevant businesses.

2. Business Lead Discovery

The Apify Places Scraper searches Google Places based on the provided business type and location.

It collects information such as:

* Business name
* Business category
* Website
* Phone number
* Physical address
* Business rating
* Number of reviews

This removes the need to manually search for potential leads.

3. Website Validation

The Filter Valid Websites node checks whether each business has a usable website.

Businesses without a valid website are filtered out before moving further through the workflow.

This helps ensure that the next AI step receives useful business information.

4. AI-Powered Email Extraction

The workflow sends the business name and website to Google Gemini.

Gemini analyzes the available business information and attempts to identify the primary public business email address.

The result is returned in a structured JSON format containing the email address.

5. Email Validation

The Parse Email JSON node processes Gemini’s response and extracts the email address.

The Has Valid Email? node then checks whether a usable email address was found.

If a valid email exists, the lead continues through the workflow.

If no email is found, the lead is automatically discarded.

6. Lead Management with Google Sheets

Valid leads are stored in Google Sheets before the outreach process begins.

The workflow records information such as:

* Company name
* Business category
* Website URL
* Email address
* Phone number
* Physical address
* Cold email status
* Send time

The initial status is set to Pending, making it easy to track each lead.

7. Lead-by-Lead Processing

The Loop Over Items node processes the leads individually.

This allows the workflow to handle each lead separately instead of trying to process every lead at once.

It also makes it possible to generate and send a personalized email for each business.

8. AI-Powered Cold Email Generation

The OpenAI Draft Generator uses GPT-4.1 Mini to create a personalized cold email for each lead.

The AI considers details such as:

* Company name
* Business type
* Target location
* Website
* Business rating
* Number of reviews

The generated email is designed to be:

* Short
* Professional
* Friendly
* Personalized
* Non-pushy
* Focused on a clear call-to-action

The workflow also instructs the AI to keep the email under 120 words.

9. Email Data Preparation

The Prepare Email Data node organizes the generated email and prepares the information required for sending.

It stores:

* Cold email content
* Recipient email
* Company name
* Current status

This keeps the email data structured before it reaches Gmail.

10. Automated Gmail Outreach

The Send Cold Email (Gmail) node sends the generated email through Gmail.

The subject is dynamically created using the company name, while the email body contains the AI-generated personalized message.

This removes the need to manually write and send each cold email.

11. Updating Lead Status

After the email is sent, the Update Sheet Status & Time node updates the corresponding lead in Google Sheets.

The status changes from:

Pending → Completed

The workflow also records the exact sending time using the Asia/Karachi timezone.

12. Controlled Processing

After each email is sent, the workflow waits for 2 seconds before continuing.

This creates a controlled processing flow and prevents the workflow from immediately moving through every lead without a pause.

🧠 AI Used in the Workflow

Google Gemini

Gemini is used for business email extraction.

It receives the business name and website and attempts to identify a public business email address.

OpenAI GPT-4.1 Mini

OpenAI is used for personalized cold email generation.

It takes the collected lead information and creates a short outreach email tailored to the specific business.

Using AI for these two different tasks makes the workflow more efficient while keeping each step focused.

🛠️ Tech Stack

Automation: n8n

Lead Discovery: Apify Google Places Scraper

AI Email Extraction: Google Gemini

AI Email Generation: OpenAI GPT-4.1 Mini

Email Delivery: Gmail

Lead Management: Google Sheets

API Integration: HTTP Request

Data Processing: JavaScript

🔄 Complete Workflow

Webhook Trigger → Apify Places Scraper → Filter Valid Websites → Gemini Email Extractor → Parse Email JSON → Validate Email → Google Sheets → Loop Over Leads → OpenAI Email Generator → Prepare Email Data → Gmail → Update Sheet → Wait → Next Lead

💡 Key Features

* Automated local business lead generation
* Google Places data collection
* Website validation
* AI-powered email extraction
* Email validation
* AI-generated personalized cold emails
* Automated Gmail outreach
* Google Sheets lead management
* Lead status tracking
* Automated timestamp recording
* Lead-by-lead processing
* Controlled email sending
* Multiple API integrations

🎯 Why I Built This

Lead generation can involve a lot of repetitive work — finding businesses, checking websites, looking for contact information, writing outreach emails, sending them, and maintaining lead records.

LeadScoutAI brings these steps into one automated workflow.

Instead of manually handling every lead, the system can discover potential businesses, collect their information, identify public contact emails, create personalized outreach, send the emails, and update the lead database automatically.

👨‍💻 Skills Demonstrated

This project demonstrates hands-on experience with:

* AI workflow automation
* n8n
* API integration
* Webhooks
* Apify
* Google Places data
* Google Gemini
* OpenAI
* Prompt engineering
* JavaScript
* Gmail automation
* Google Sheets automation
* Lead generation
* B2B cold outreach
* Data validation
* Workflow branching
* Automated lead tracking

🚀 Project Outcome

LeadScoutAI demonstrates how AI and automation can be combined to create a practical B2B lead generation and outreach system.

From finding potential businesses to generating personalized emails and tracking the outreach process, the workflow minimizes repetitive manual tasks and creates a more structured approach to lead generation.
