# Setup Guide

## Prerequisites

Before running the workflow, ensure you have the following:

- n8n (Cloud or Self-hosted)
- OpenAI API Key
- Tavily API Key
- Gmail Account (or SMTP credentials)
- Internet connection

---

# Project Structure

```
AI-Research-Agent/
│
├── workflow/
│   └── AI_Research_Agent.json
│
├── prompts/
│   └── summarization_prompt.md
│
├── assets/
│
├── docs/
│
└── README.md
```

---

# Installation

## Step 1: Clone the Repository

```bash
git clone https://github.com/<your-username>/AI-Research-Agent.git
```

```bash
cd AI-Research-Agent
```

---

## Step 2: Open n8n

You can use either:

- n8n Cloud
- Self-hosted n8n
- Local Desktop Installation

---

## Step 3: Import the Workflow

1. Open n8n.
2. Click **Import Workflow**.
3. Select:

```
workflow/AI_Research_Agent.json
```

The complete workflow will be imported into your workspace.

---

# Configure Credentials

## OpenAI

Create an OpenAI credential inside n8n.

Required:

- OpenAI API Key

Connect the credential to the **Summarize News** node.

---

## Tavily

Create an HTTP Request credential (or configure the API key directly in the HTTP Request node).

Required:

- Tavily API Key

Update the API key before executing the workflow.

---

## Gmail

Create a Gmail credential.

Authorize your Google account.

Connect it to the **Send Email** node.

---

# Workflow Configuration

## Schedule Trigger

Configure:

- Frequency: Daily
- Time: 7:00 AM (or your preferred time)

---

## Search Query

Modify the Tavily query to search for your preferred topics.

Example:

- Artificial Intelligence
- Machine Learning
- LLMs
- Robotics
- AI Startups
- OpenAI
- Google DeepMind

---

## Email Recipient

Update the Gmail node with your recipient email address.

---

# Running the Workflow

### Manual Execution

Click

```
Execute Workflow
```

The workflow will:

1. Search the latest AI news.
2. Process and clean the results.
3. Generate summaries using OpenAI.
4. Build an HTML newsletter.
5. Send the newsletter via Gmail.

---

### Automatic Execution

Publish the workflow in n8n.

The Schedule Trigger will execute automatically based on the configured schedule.

---

# Expected Output

After successful execution, you will receive a professionally formatted HTML email containing:

- Top AI news stories
- Importance score
- Category
- Source
- Summary
- Why it matters
- Direct article links

---

# Troubleshooting

## No News Retrieved

- Verify the Tavily API key.
- Check the search query.
- Ensure the API limit has not been exceeded.

---

## OpenAI Errors

- Verify your API key.
- Check API usage and quota.
- Ensure the selected model is available.

---

## Gmail Authentication Failed

- Reconnect Gmail credentials.
- Verify OAuth permissions.
- Ensure Gmail API access is enabled.

---

## HTML Email Formatting Issues

- Verify the HTML generation node.
- Confirm that the LLM returns valid JSON output.
- Check for malformed HTML.

---

# Customization

You can easily customize the workflow by changing:

- Search query
- Email template
- Schedule
- AI prompt
- Number of news articles
- LLM model
- Output format

---

# Future Improvements

Planned enhancements include:

- Multi-Agent AI Architecture
- Article Image Extraction
- Fact Verification Agent
- Personalized News Feed
- Historical News Database
- Web Dashboard
- Slack & Microsoft Teams Integration

---

# Support

If you encounter issues while configuring the workflow, verify that all credentials are correctly configured and that each workflow node is connected properly.

Refer to the main README for an overview of the project architecture and workflow.