# AI Research Agent Architecture

## Overview

The AI Research Agent is an automated AI-powered news curation workflow that discovers the latest Artificial Intelligence news, processes it using a Large Language Model (LLM), and delivers a professionally formatted HTML newsletter via email.

The system is built using **n8n** and follows a modular pipeline architecture where each node performs a single responsibility.

---

## High-Level Architecture
Schedule Trigger
↓
Tavily Search API
↓
JavaScript Data Processing
↓
OpenAI GPT Model
↓
HTML Email Generator
↓
Gmail


---

# Architecture Components

## 1. Schedule Trigger

**Purpose**

Automatically starts the workflow every day at the configured time.

**Responsibilities**

- Trigger workflow execution
- Enable unattended automation
- Support scheduled delivery

---

## 2. Tavily Search API

**Purpose**

Collect the latest AI-related news articles published during the last 24 hours.

**Responsibilities**

- Search the web
- Retrieve article metadata
- Return article URLs
- Return snippets

**Output**

- Article title
- URL
- Content snippet

---

## 3. Data Cleaning Layer

Implemented using a JavaScript Code Node.

**Purpose**

Transform raw Tavily results into structured text suitable for LLM processing.

**Responsibilities**

- Extract titles
- Extract URLs
- Extract snippets
- Remove unnecessary fields
- Prepare prompt input

This layer acts as an ETL (Extract–Transform–Load) stage.

---

## 4. OpenAI GPT Model

This is the intelligence layer of the workflow.

Instead of forwarding raw news articles, the model performs AI-powered content curation.

Responsibilities include:

- Removing duplicate news
- Ranking stories by importance
- Categorizing articles
- Generating concise summaries
- Explaining why each article matters
- Producing structured JSON output

Example output:

- Title
- URL
- Category
- Importance Score
- Summary
- Impact
- Source

---

## 5. HTML Email Generator

A JavaScript node converts the structured JSON into a responsive HTML newsletter.

Features include:

- AI-themed header
- Publication date
- Importance score
- Category
- Source
- Summary
- Why It Matters section
- Article links
- Professional styling

---

## 6. Gmail Integration

The final stage delivers the generated newsletter directly to the recipient's inbox.

The workflow can execute automatically every day without manual intervention.

---

# Data Flow

1. Schedule Trigger starts the workflow.

2. Tavily searches for the latest AI news.

3. Search results are cleaned and formatted.

4. OpenAI processes the articles and generates structured summaries.

5. HTML content is dynamically generated.

6. Gmail sends the newsletter.

---

# Technology Stack

## Technology Stack

| Component | Technology |
|------------|------------|
| Workflow Automation | n8n |
| AI Orchestration | n8n AI Nodes |
| Large Language Model (LLM) | OpenAI GPT-5 Mini |
| Web Search API | Tavily Search API |
| Programming Language | JavaScript |
| Data Processing | JSON |
| Email Service | Gmail API |
| Prompt Engineering | Structured JSON Prompting |
| Output Format | Responsive HTML Email |
| Workflow Trigger | Schedule Trigger |
| Version Control | Git & GitHub |
---

# Design Principles

The workflow follows a modular architecture where every node performs a single responsibility.

Benefits include:

- Easy maintenance
- Clear separation of concerns
- Reusable workflow components
- Extensible architecture
- Production-ready automation

---

# Future Architecture

The current implementation uses a single AI reasoning stage.

Future versions will evolve into a multi-agent architecture consisting of:

- Search Agent
- Verification Agent
- Ranking Agent
- Summarization Agent
- Newsletter Agent

This evolution will improve scalability, explainability, and autonomous decision-making while maintaining the modular workflow design.