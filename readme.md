# 🧠 Multi-Agent Research System with PDF Report Generation
![working](https://github.com/user-attachments/assets/3327eca6-4101-48fe-8dfb-5968dc30bca2)

This project implements an automated research system that processes user queries and generates professional PDF reports using a multi-agent architecture powered by the Groq API.


## 📌 Overview

The system transforms an input query into a structured, human-readable PDF report (300–500 words). It uses Groq's LLM to decompose the query, scrape relevant content from the web, summarize findings, and generate a styled PDF document - all in memory.


## ⚙️ Core Requirements

### ✅ Input / Output

- **Input**: Research query string (e.g., `"Impact of AI in healthcare"`)
- **Output**: PDF report with 3–5 sections based on sub-queries

## 🧱 System Architecture

### 🧩 Agent 1: Query Processor
- Uses Groq API to decompose user query into 3–5 focused sub-queries
- Removes duplicates and checks relevance to the main query
- Handles vague or single-word queries with fallback logic

### 🌐 Agent 2: Data Collector
- Searches and scrapes 2–3 web sources per sub-query
- Extracts clean, structured content (500–1000 words per source)
- Removes irrelevant content (ads, navigation bars, etc.)
- Handles scraping failures and implements basic rate limiting

### 📚 Agent 3: Content Analyzer
- Synthesizes collected data using Groq API
- Structures content into 3–4 main sections
- Ensures summaries are coherent, within Groq's context limits (~4000 characters)
- Highlights key insights and findings per topic

### 📝 Agent 4: Report Generator
- Generates professional PDF report using ReportLab
- Includes:
  - Title page with query and date
  - Structured sections with headings and paragraphs
  - Optional source citations
- Performs quality checks (word count, formatting, structure)

## 🛠️ Technical Stack

- **Language**: Python 3.8+
- **LLM**: [Groq API](https://console.groq.com/docs)
- **Web Scraping**: Playwright, BeautifulSoup
- **PDF Generation**: ReportLab
- **Env Management**: python-dotenv

## 🔧 Setup Instructions

### 1. Clone Repository

```bash
git clone https://github.com/yourusername/multi-agent-research-system.git
cd multi-agent-research-system


## 📂 Project Structure
├── agents/
│   ├── query_processor.py
│   ├── data_collector.py
│   ├── content_analyzer.py
│   └── report_generator.py
├── browser.py
├── groq_client.py
├── main.py
├── .env
├── requirements.txt
├── README.md
└── sample_outputs/
    └── ai_in_education_report.pdf
