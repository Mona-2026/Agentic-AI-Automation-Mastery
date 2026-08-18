AI SOC Memory & Incident Response Automation

An AI-powered Security Operations Center (SOC) workflow built with n8n that automates security incident ingestion, threat intelligence enrichment, AI-based analysis, historical incident comparison, response recommendations, reporting, and incident memory.

The workflow is designed to help SOC teams process security logs faster, identify the severity of incidents, enrich indicators with external threat intelligence, and reuse knowledge from previously investigated incidents.

Workflow Overview

The workflow starts when a security log or incident file is submitted through an n8n Webhook.

The uploaded file is processed and its contents are extracted for analysis. JavaScript is then used to identify important Indicators of Compromise (IOCs), including IP addresses, MD5 and SHA-256 hashes, URLs, usernames, and hostnames.

The workflow then determines the potential incident category from the log, such as PowerShell execution, malware activity, brute-force attempts, or phishing-related activity.

Threat Intelligence Enrichment

Extracted IOCs are enriched using multiple external threat intelligence sources.

The workflow integrates with VirusTotal to investigate file hashes, AbuseIPDB to check suspicious IP addresses, and GreyNoise to determine whether IP addresses are associated with known internet scanning or malicious activity.

It also retrieves data from MITRE ATT&CK, providing additional context for understanding attacker behavior and techniques.

These results are combined before being passed to the AI incident analysis stage.

AI Incident Analysis

The enriched incident data is analyzed by OpenAI GPT-4.1 Mini.

The Incident Analyzer evaluates the raw security log, extracted IOCs, and threat intelligence results to determine:

* Attack category
* Incident severity
* Severity score
* MITRE ATT&CK mapping
* Root-cause summary
* Affected assets
* Confidence score

The AI is instructed to base its analysis strictly on the evidence provided rather than inventing missing information.

AI SOC Memory

One of the key features of this workflow is its AI-powered incident memory.

After an incident is analyzed, the workflow converts the incident information into an embedding using OpenAI Embeddings and stores it in a Pinecone vector database.

When a new incident arrives, its root-cause summary is compared against previously stored incidents using vector similarity search.

This allows the workflow to identify whether the current incident resembles something the SOC has encountered before.

Historical Incident Comparison

If a sufficiently similar historical incident is found, the Comparison Agent analyzes both incidents.

It identifies:

* Shared indicators
* New or changed indicators
* Important differences
* Whether the attack is a repeat, variant, or evolved attack
* Which successful actions from the previous incident can potentially be reused

If no strong historical match is found, the workflow treats the incident as a new or first-seen pattern.

AI-Generated Response Recommendations

The Recommendation Agent generates a prioritized mitigation playbook for the SOC team.

The recommendations cover immediate containment, investigation, remediation, and escalation criteria.

When a relevant historical incident exists, the agent can use previously successful resolution steps as part of the recommended response.

This turns the workflow from a simple alert analyzer into a system that can continuously learn from previous incident investigations.

Automated SOC Reporting

The Reporting Agent converts the analysis and recommended response into a concise executive-level incident briefing.

The generated report includes the incident severity, business impact, historical context, and recommended immediate actions.

The workflow then automatically sends the report through Gmail so that the relevant team can be notified without manually preparing an incident summary.

Incident Database

Important incident information is stored in Supabase.

The stored information includes the incident ID, category, severity, similarity score, summary, resolution status, vector ID, confidence, and severity metrics.

This provides a structured record of incidents while Pinecone maintains the semantic memory used for historical similarity searches.

Incident Documentation

The workflow also uploads the generated incident report to Google Drive.

This creates a persistent documentation layer where incident reports can be stored and accessed by the SOC team for future investigations, audits, and knowledge reuse.

Tech Stack

The workflow is built using:

n8n for workflow automation and orchestration.

OpenAI GPT-4.1 and GPT-4.1 Mini for incident analysis, comparison, recommendations, and reporting.

OpenAI Embeddings for converting incident information into searchable vector representations.

Pinecone for AI-powered historical incident memory and similarity search.

Supabase for structured incident storage.

VirusTotal, AbuseIPDB, GreyNoise, and MITRE ATT&CK for threat intelligence and security context.

Google Drive for incident report storage.

Gmail for automated SOC notifications.

JavaScript for log processing and IOC extraction.

Key Capabilities

This workflow provides an end-to-end automated SOC pipeline that can:

* Ingest security logs through a webhook
* Extract and normalize security data
* Automatically identify IOCs
* Enrich incidents with multiple threat intelligence sources
* Analyze incidents using AI
* Map attacks to MITRE ATT&CK techniques
* Assign severity and confidence scores
* Search historical incidents using vector similarity
* Compare new incidents with previous attacks
* Reuse successful historical response strategies
* Generate actionable mitigation playbooks
* Create executive-friendly incident reports
* Store incidents in Supabase
* Build long-term AI-powered SOC memory with Pinecone
* Save incident documentation to Google Drive
* Automatically notify the SOC team through email

Why This Workflow Matters

Traditional SOC workflows often require analysts to manually investigate alerts, search threat intelligence platforms, compare previous incidents, prepare reports, and decide on appropriate response actions.

This automation brings those steps together into a single AI-assisted pipeline.

Instead of treating every security incident as a completely new problem, the system can learn from previous incidents, recognize similar attack patterns, and reuse proven response knowledge.

The result is a more consistent, faster, and knowledge-driven incident response process.
