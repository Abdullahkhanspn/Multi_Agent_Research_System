# Multi-Agent Research System

An automated research system that processes user queries and generates professional PDF reports using a 4-agent architecture with Groq API.

## 🏗️ Architecture

### Agent 1: Query Processor

- Decomposes user queries into 3-5 focused sub-queries
- Validates sub-queries for relevance and specificity
- Handles edge cases (vague queries, single-word inputs)

### Agent 2: Data Collector

- Searches and scrapes 2-3 web sources per sub-query
- Extracts relevant content (500-1000 words per source)
- Implements rate limiting and error handling

### Agent 3: Content Analyzer

- Synthesizes collected data into coherent summary
- Structures content with clear sections
- Handles Groq's context limits (truncates to ~4000 chars)

### Agent 4: Report Generator

- Creates professional PDF reports
- Includes title page with query and date
- Performs basic quality checks

## Setup

### 1. Install Dependencies

```bash
pip install -r requirements.txt
playwright install chromium
```
