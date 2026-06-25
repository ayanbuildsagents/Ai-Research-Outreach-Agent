# 🔍 AI Research & Outreach Agent

> Autonomous AI agent that reads clinic websites, detects business pain points, and generates hyper-personalized cold outreach emails — all saved to Google Sheets automatically.

## 🔥 What It Does

Feed it a list of clinic URLs → it visits each website → reads all pages → extracts contact info + services + booking method → identifies pain points → drafts a personalized cold email for each clinic → saves everything to Google Sheets. Fully automated.

## 🧠 How It Works

| Step | What Happens |
|------|-------------|
| 1 | Reads clinic URLs from Google Sheets (Lead List) |
| 2 | Loops through each clinic one by one |
| 3 | AI web agent visits the website — reads Home, About, Services, Contact, Booking pages |
| 4 | Extracts: clinic name, services, founder name, email, phone, booking method |
| 5 | Detects pain points: no online booking, no chatbot, missed calls, no follow-up automation |
| 6 | Drafts a personalized cold email specific to their pain point |
| 7 | Appends all data + email draft to output Google Sheet |

## 🛠️ Built With

- **n8n** — workflow automation + loop handling
- **TinyFish AI Agent** — autonomous web browsing & data extraction
- **Google Sheets API** — input lead list + output storage
- **JavaScript (Code node)** — SSE response parsing + JSON extraction

## 💡 Key Features

- Visits real websites autonomously — not just scraping HTML
- Detects specific pain points per clinic (no guessing)
- Email drafted around their actual problem — not a generic template
- Handles SSE streaming response from AI agent
- Batch processes unlimited clinics via loop
- Output sheet has: clinic info + pain points + email subject + full email body

## 📋 Setup

1. Import `RESEARCH_AGENT.json` into your n8n instance
2. Add credentials: Google Sheets OAuth2, TinyFish AI API key
3. Create input Sheet with column: `Website URL`
4. Create output Sheet with columns: `Clinic Name`, `Clinic Summary`, `Services Offered`, `Founder / Doctor Name`, `Contact Email`, `Contact Phone`, `Booking Method Found`, `Pain Points (AI Detected)`, `Email Subject Line`, `Email Body (Draft)`
5. Run manually — agent processes all URLs automatically

## 📁 Files

| File | Description |
|------|-------------|
| `RESEARCH_AGENT.json` | Complete n8n workflow — ready to import |
