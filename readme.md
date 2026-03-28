# 📄 PDF to Summary Bot — n8n Telegram Workflow

Automatically summarize any PDF document by sending it to a Telegram bot. Powered by n8n automation and GPT-4o Mini.

---

## 🚀 What It Does

Send a PDF file to your Telegram bot → get a clean, structured summary back in seconds. No manual copy-pasting. No complex setup. Just send and read.

---

## 🔄 Workflow Overview

```
Telegram (PDF received)
        ↓
Extract Text from PDF
        ↓
GPT-4o Mini summarizes content
        ↓
Telegram (summary sent back)
```

<img src="pdf_to_summary_n8n_workflow.html" alt="Description" width="100" />

---

## 🧩 Nodes Breakdown

| Node | Type | Purpose |
|------|------|---------|
| **Telegram Trigger** | Trigger | Listens for incoming messages with file attachments |
| **Extract from File** | Transform | Extracts raw text from the uploaded PDF |
| **Message a Model** | AI (OpenAI) | Sends extracted text to GPT-4o Mini for summarization |
| **Send a text message** | Output | Sends the generated summary back to the user on Telegram |

---

## ⚙️ Configuration

### Prerequisites

- [n8n](https://n8n.io/) instance (self-hosted or cloud)
- Telegram Bot Token ([create via BotFather](https://t.me/BotFather))
- OpenAI API Key

### Credentials Required

| Credential | Used By |
|-----------|---------|
| `Telegram API` | Telegram Trigger + Send Message nodes |
| `OpenAI API` | Message a Model node |

### Settings

- **Binary Mode:** `separate` (required for file handling)
- **Execution Order:** `v1`
- **Telegram Trigger:** Downloads attachments automatically (`download: true`)

---

## 🤖 AI Prompt

The model is instructed to:

> Summarize the content in simple human-readable format with **sections** instead of lengthy or very short responses. Each section contains a maximum of **2 lines**.

Model used: **GPT-4o Mini** — fast, cost-effective, and great for summarization tasks.

---

## 📦 How to Import

1. Copy the workflow JSON
2. Open your n8n instance
3. Go to **Workflows → Import from JSON**
4. Paste the JSON and click **Import**
5. Add your credentials to the Telegram and OpenAI nodes
6. **Activate** the workflow

---

## 💬 How to Use

1. Open your Telegram bot
2. Send any PDF file (research paper, report, document, etc.)
3. Wait a few seconds
4. Receive a structured summary directly in the chat ✅

---

## 🛠️ Customization Ideas

- **Language:** Add a language instruction to summarize in Tamil, Hindi, or any language
- **Length:** Adjust the prompt to make summaries shorter or more detailed
- **Format:** Request bullet points, numbered lists, or executive summaries
- **Model:** Swap GPT-4o Mini for GPT-4o for higher accuracy on complex documents
- **Multi-format:** Extend the Extract node to support DOCX or TXT files

---

## 📁 File Structure

```
n8n-pdf-summary-telegram/
├── workflow.json          ← Import this into n8n
└── README.md              ← You are here
```

---

## 👤 Author

Vignesh Nagarajan - AI Engineer

---

## 📄 License

MIT — free to use, modify, and share.