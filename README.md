# AI Email Assistant with n8n

An intelligent email management system that automatically retrieves, summarizes, and categorizes Gmail messages using n8n workflows, 
Supabase, and OpenAI — enabling users to save hours daily by quickly identifying which emails to prioritize.

## Project Overview

With email overload becoming a productivity bottleneck, this project solves the issue by building a low-code AI email assistant. It uses **n8n** to automate two workflows:

1. **Email Fetcher Workflow**: Retrieves Gmail messages and appends them to a **Supabase** database for further processing.
2. **Summarizer Workflow**: Utilizes **OpenAI's GPT API** to generate concise 15-word summaries and categorize emails (e.g., Work, Promotions, Personal, Spam).

The goal is to enable users to scan through summaries and decide which emails are worth reading, saving **up to 3+ hours per day**.

---

## Features

- 🔄 Automated Gmail integration using n8n.
- 🗂️ Email storage in Supabase PostgreSQL tables.
- ✨ AI-based summarization of full email bodies (15 words max).
- 🏷️ Smart classification into categories for better triage.
- ⏱️ Saves up to 60% time in email processing and prioritization.

---

## 🛠️ Technologies Used

- **n8n** – Low-code automation platform
- **Supabase** – PostgreSQL-based backend (database + API)
- **OpenAI API** – For summarization and categorization
- **Gmail API** – For fetching emails
- 
---

## 📊 Workflow Architecture

### 1️⃣ Workflow: Email Fetcher

- Authenticates with Gmail API using OAuth 2.0
- Fetches unread emails
- Parses metadata (subject, sender, date, body)
- Inserts parsed data into Supabase table

### 2️⃣ Workflow: Summarizer & Classifier

- Triggers on new database row in Supabase
- Sends email body to OpenAI
- Receives:
  - 15-word summary
  - Predicted category
- Updates the record with summary and category

---

