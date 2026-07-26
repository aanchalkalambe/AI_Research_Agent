# Workflow Explanation

## Overview

The **AI Research Agent** is an automated workflow built with **n8n** that discovers the latest Artificial Intelligence news, processes it using a Large Language Model (LLM), and delivers a professionally formatted HTML newsletter via email.

The workflow is designed using a modular architecture where each node performs a specific responsibility, making the system easy to understand, maintain, and extend.

---

# Workflow Overview

```text
Schedule Trigger
        │
        ▼
Search AI News (Tavily API)
        │
        ▼
Clean Search Results
        │
        ▼
Summarize News (OpenAI GPT)
        │
        ▼
Build HTML Email
        │
        ▼
Send Email (Gmail)
```

---

# Workflow Steps

## 1. Schedule Trigger

### Purpose

Automatically starts the workflow at a predefined time every day.

### Responsibilities

- Executes the workflow automatically.
- Eliminates manual intervention.
- Ensures daily newsletter delivery.

### Input

None

### Output

Workflow execution event.

---

## 2. Search AI News (Tavily API)

### Purpose

Retrieve the latest AI-related news articles from across the web.

### Responsibilities

- Search for AI news published within the last 24 hours.
- Collect recent and relevant articles.
- Retrieve article metadata.

### Input

Search query:

- Artificial Intelligence
- LLMs
- OpenAI
- Anthropic
- Google DeepMind
- Robotics
- AI Startups
- AI Regulation

### Output

A JSON array containing:

- Title
- URL
- Content Snippet

---

## 3. Clean Search Results

### Purpose

Prepare the retrieved news articles for AI processing.

### Responsibilities

- Extract important fields.
- Remove unnecessary metadata.
- Format articles into a structured text block.
- Prepare a clean prompt for the language model.

### Implementation

JavaScript Code Node

### Output

Formatted news data ready for the LLM.

---

## 4. Summarize News (OpenAI GPT)

### Purpose

Act as an AI news editor that analyzes and curates the retrieved articles.

### Responsibilities

- Remove duplicate stories.
- Rank news by importance.
- Categorize each article.
- Generate concise summaries.
- Explain why each story matters.
- Return structured JSON output.

### Example Output

```json
{
  "title": "...",
  "url": "...",
  "category": "...",
  "importance": 9.5,
  "summary": "...",
  "impact": "...",
  "source": "..."
}
```

---

## 5. Build HTML Email

### Purpose

Convert the structured JSON into a visually appealing HTML newsletter.

### Responsibilities

Generate:

- Professional header
- Current date
- Article cards
- Importance score
- Category
- Source
- Summary
- Why It Matters section
- Read Article button
- Footer

### Output

Responsive HTML email.

---

## 6. Send Email (Gmail)

### Purpose

Deliver the generated newsletter to the user's inbox.

### Responsibilities

- Send HTML email.
- Preserve formatting.
- Automate daily delivery.

### Output

Daily AI newsletter.

---

# Data Flow

The workflow follows a linear pipeline:

1. Schedule Trigger initiates execution.
2. Tavily Search retrieves the latest AI news.
3. JavaScript cleans and structures the retrieved data.
4. OpenAI processes the articles and generates structured summaries.
5. JavaScript converts the summaries into a professional HTML newsletter.
6. Gmail delivers the newsletter automatically.

---

# Input and Output

## Input

Latest AI news retrieved from Tavily Search API.

## Processing

- Search
- Cleaning
- Ranking
- Categorization
- Summarization
- HTML Generation

## Output

A professionally formatted AI newsletter delivered via Gmail.

---

# Current Features

- Automated daily execution
- Real-time AI news retrieval
- AI-powered summarization
- Duplicate removal
- Importance ranking
- News categorization
- HTML newsletter generation
- Gmail integration
- Structured JSON processing

---

# Future Improvements

The current workflow represents Version 1 of the project.

Planned enhancements include:

- Multi-Agent Architecture
- Fact Verification Agent
- Personalized News Recommendations
- AI Memory for Previously Sent Articles
- Article Image Extraction
- Slack & Discord Integration
- Web Dashboard
- Database Storage for Historical News
- Analytics & Performance Tracking

---

# Workflow Summary

The AI Research Agent demonstrates how workflow automation and Large Language Models can be combined to create an autonomous AI-powered news curation system.

By integrating web search, prompt engineering, structured data processing, and automated email delivery, the workflow transforms raw news articles into a concise, informative, and visually appealing daily newsletter with minimal human intervention.