<p align="center">
  <img src="assets/cover.png" alt="AI Research Agent Banner" width="100%">
</p>

<br>
# 🤖 AI Research Agent

<p align="center">
  <strong>An AI-powered autonomous news research and newsletter generation workflow built with n8n, OpenAI, and Tavily.</strong>
</p>

<p align="center">
Automatically discovers the latest AI news, removes duplicates, ranks stories by impact, summarizes them using an LLM, and delivers a beautiful HTML newsletter directly to your inbox.
</p>

<p align="center">

![n8n](https://img.shields.io/badge/n8n-Workflow%20Automation-EA4B71?style=for-the-badge&logo=n8n)

![OpenAI](https://img.shields.io/badge/OpenAI-GPT--5-412991?style=for-the-badge&logo=openai)

![Tavily](https://img.shields.io/badge/Tavily-Web%20Search-blue?style=for-the-badge)

![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

![GitHub](https://img.shields.io/badge/Open%20Source-GitHub-181717?style=for-the-badge&logo=github)

</p>

---

# 📖 Overview

AI Research Agent is an end-to-end workflow automation project that transforms raw web search results into a curated daily AI newsletter.

Instead of simply collecting links, the workflow intelligently:

- Searches the web for the latest AI news
- Filters duplicate and low-quality articles
- Ranks stories by importance
- Generates concise summaries
- Explains why each story matters
- Produces a professional HTML newsletter
- Sends the newsletter automatically via Gmail

The project demonstrates how Large Language Models can be integrated into workflow automation systems to perform structured information retrieval, reasoning, and content generation with minimal human intervention.

---

# ✨ Features

- 🔍 Automated AI news discovery using Tavily Search API
- 🧠 AI-powered article ranking and summarization
- 📰 Professional newsletter generation
- 📧 Automated Gmail delivery
- 📅 Daily scheduled execution
- 📊 Importance-based news ranking
- 🗂️ AI news categorization
- 🔁 Duplicate article removal
- 🎨 Responsive HTML email template
- ⚡ Built using low-code workflow automation (n8n)

---

# 🏗️ System Architecture

<p align="center">
<img src="assets/architecture.png" width="850">
</p>

The workflow follows a modular pipeline architecture:

```
Schedule Trigger
        │
        ▼
Tavily Search API
        │
        ▼
Data Cleaning
(JavaScript)
        │
        ▼
OpenAI GPT
(Summarization & Ranking)
        │
        ▼
HTML Newsletter Generator
        │
        ▼
Gmail
```

Each stage has a single responsibility, making the workflow modular, maintainable, and easy to extend.

---

# 🔄 Workflow

<p align="center">
<img src="assets/workflow.png" width="1000">
</p>

The workflow consists of six major stages:

| Step | Description |
|------|-------------|
| 1 | Schedule Trigger starts the workflow |
| 2 | Tavily searches for recent AI news |
| 3 | JavaScript cleans and formats the results |
| 4 | OpenAI ranks and summarizes the articles |
| 5 | HTML email is dynamically generated |
| 6 | Gmail sends the final newsletter |

---

# 📨 Sample Newsletter

<p align="center">
<img src="assets/newsletter.png" width="850">
</p>

The generated newsletter includes:

- Importance Score
- AI Category
- News Source
- Professional Summary
- Why It Matters
- Direct Article Link

---

# 🚀 Tech Stack

| Category | Technology |
|------------|------------|
| Workflow Automation | n8n |
| AI Model | OpenAI GPT |
| Search API | Tavily Search API |
| Programming Language | JavaScript |
| Data Processing | JSON |
| Email Service | Gmail |
| Prompt Engineering | Structured Prompting |
| Output | HTML Newsletter |
| Version Control | Git & GitHub |

---

# 📂 Project Structure

```text
AI_Research_Agent/
│
├── workflow/
│   └── AI_Research_Agent.json
│
├── prompts/
│   └── summarization_prompt.md
│
├── docs/
│   ├── architecture.md
│   ├── workflow-explanation.md
│   └── setup-guide.md
│
├── examples/
│   ├── sample-output.json
│   └── sample-email.html
│
├── assets/
│   ├── architecture.png
│   ├── workflow.png
│   └── newsletter.png
│
├── README.md
├── ROADMAP.md
├── CHANGELOG.md
├── LICENSE
└── .gitignore
```

---

# ⚙️ Installation

## Prerequisites

Before running the workflow, ensure you have:

- n8n (Cloud or Self-hosted)
- OpenAI API Key
- Tavily API Key
- Gmail Account
- Internet Connection

---

## Clone the Repository

```bash
git clone https://github.com/aanchalkalambe/AI_Research_Agent.git

cd AI_Research_Agent
```

---

## Import the Workflow

1. Open n8n.
2. Click **Import Workflow**.
3. Select:

```
workflow/AI_Research_Agent.json
```

4. Import the workflow.

---

## Configure Credentials

### OpenAI

Add your OpenAI API Key inside n8n.

Connect it to the **Summarize News** node.

---

### Tavily

Add your Tavily API Key.

Connect it to the HTTP Request node.

---

### Gmail

Authenticate your Gmail account using OAuth.

Connect the Gmail credential to the **Send Email** node.

---

# ▶️ Running the Workflow

### Manual Execution

Click **Execute Workflow** inside n8n.

The workflow will:

- Search the latest AI news
- Remove duplicate stories
- Rank stories by importance
- Generate concise summaries
- Build an HTML newsletter
- Send the newsletter via Gmail

---

### Scheduled Execution

Publish the workflow in n8n.

The Schedule Trigger will automatically execute the workflow at the configured time.

---

# 📊 Sample Output

Example JSON generated by the AI model:

```json
[
  {
    "title": "OpenAI releases new GPT model",
    "category": "LLMs",
    "importance": 9.8,
    "summary": "OpenAI announced a new frontier model with improved reasoning capabilities.",
    "impact": "Developers can build more capable AI applications using the latest model.",
    "source": "OpenAI"
  }
]
```

The complete examples are available in:

```
examples/
├── sample-output.json
└── sample-email.html
```

---

# 📚 Documentation

Detailed documentation is available in the `docs/` directory.

| Document | Description |
|----------|-------------|
| architecture.md | System architecture and design |
| workflow-explanation.md | Step-by-step workflow explanation |
| setup-guide.md | Installation and configuration guide |

---

# 🎯 Use Cases

This project can be adapted for:

- Daily AI News Digest
- Research Paper Summarization
- Company Intelligence Reports
- Startup Monitoring
- Competitor Analysis
- Technology Trend Tracking
- Automated Newsletters
- Knowledge Management Systems

---

# 🛣️ Roadmap

## ✅ Version 1.0

- Automated AI news search
- AI-powered summarization
- HTML newsletter generation
- Gmail integration
- Daily scheduled execution

---

## 🚀 Version 1.1

- Better duplicate detection
- Improved ranking algorithm
- Dark mode email template
- Configurable newsletter size

---

## 🤖 Version 2.0

- Multi-Agent Architecture
- Search Agent
- Verification Agent
- Ranking Agent
- Summarization Agent
- Newsletter Agent

---

## 🌍 Version 3.0

- Personalized newsletters
- Slack integration
- Discord integration
- Web dashboard
- Historical news database
- Analytics dashboard
- RSS feed support

---

# 💡 Future Improvements

Planned enhancements include:

- Agentic AI architecture
- Multiple LLM support
- Local LLM compatibility
- Image extraction from articles
- Fact verification agent
- Vector database integration
- Memory-enabled newsletter generation
- Multi-language support

---

# 🤝 Contributing

Contributions are welcome.

If you'd like to improve this project:

1. Fork the repository.
2. Create a feature branch.

```bash
git checkout -b feature/my-feature
```

3. Commit your changes.

```bash
git commit -m "Add new feature"
```

4. Push the branch.

```bash
git push origin feature/my-feature
```

5. Open a Pull Request.

---

# 📄 License

This project is licensed under the **MIT License**.

See the `LICENSE` file for more details.

---

# 🙏 Acknowledgements

Special thanks to the teams behind:

- n8n
- OpenAI
- Tavily Search
- Gmail API
- GitHub

for providing the tools and platforms that made this project possible.

---

# 👩‍💻 Author

**Aanchal Kalambe**

AI Engineering Student | Machine Learning | Generative AI | Agentic AI | Workflow Automation

GitHub: https://github.com/aanchalkalambe

---

# ⭐ Support

If you found this project useful:

- ⭐ Star this repository
- 🍴 Fork the project
- 🛠️ Share feedback
- 💬 Open an issue for suggestions

Your support helps improve the project and encourages future development.

---

<p align="center">
Made with ❤️ using n8n, OpenAI, and Tavily
</p>
