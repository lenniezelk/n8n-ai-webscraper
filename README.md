# n8n AI Web Scraper & Summarizer

An automated n8n workflow that accepts a web URL via a POST webhook, extracts the main article text, summarizes the content using an LLM, and returns the response synchronously.

![Workflow Preview](images/workflow-preview.png)

## 📋 Features

- **Webhook Trigger:** Asynchronous or synchronous POST endpoint.
- **HTML Parsing:** Strips scripts, styles, and tags to parse body text.
- **AI Processing:** Chunks text payload and sends to Google Gemini.

## 🚀 Quickstart

1. **Prerequisites:** A running instance of n8n (v1.0+) and a Google Gemini API key.
2. **Import the Workflow:**
   - In n8n, go to **Workflows** -> **Import from File**.
   - Select `workflows/ai-webscraper.json` from this repository.
3. **Configure Credentials:**
   - Open the **Google Gemini Chat Model** node and assign your Google Gemini API credential.
4. **Activate & Test:**
   - Toggle the workflow to **Active**.
   - Send a test payload:

```bash
curl -X POST http://localhost:5678/webhook/your-endpoint-path \
  -H "Content-Type: application/json" \
  -d '{"url": "https://en.wikipedia.org/wiki/Automation"}'
```
