# TechCast AI – Autonomous Software Engineering News & Video Pipeline

![n8n](https://img.shields.io/badge/n8n-Workflow_Automation-EA4B71?style=flat-square&logo=n8n&logoColor=white)
![Groq](https://img.shields.io/badge/Groq-LLM_Orchestration-f55036?style=flat-square)
![JavaScript](https://img.shields.io/badge/JavaScript-Custom_Nodes-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

TechCast AI is a fully autonomous, serverless data pipeline that ingests daily software engineering news from top industry feeds, curates the most relevant topics using AI, and transforms them into production-ready YouTube videos with zero human intervention.

## 🌟 Key Features

- **Zero-Touch Automation:** Runs daily on a cron schedule to aggregate, deduplicate, and score content from 10+ industry RSS feeds (GitHub Blog, freeCodeCamp, Smashing Magazine).
- **Multi-Agent Architecture:** Dynamically routes specialized tasks between **Qwen 27B** (for deep technical research and scriptwriting) and **LLaMA 3.1 8B** (for fast SEO optimization and topic scoring) to maximize inference speed and API token efficiency.
- **Self-Healing JSON Middleware:** Implements custom JavaScript nodes with complex regex state-machines to automatically sanitize LLM hallucinations and repair malformed JSON payloads, guaranteeing 100% pipeline stability.
- **Programmatic Video Generation:** Integrates directly with the **JSON2Video API** and **ElevenLabs API** to construct dynamic motion graphics, automated subtitles, and high-quality TTS audio from structured JSON payloads.

---

# ✨ Features

- 🔍 Automatic topic discovery
- 📈 AI-powered topic ranking
- 📚 Technical research
- ✍️ Script generation
- 🎙️ AI voice generation
- 🖼️ Image & screenshot generation
- 💬 Caption generation
- 🎬 Automatic video rendering
- ✅ Video quality validation
- 📺 YouTube upload automation
- 🔄 Intelligent feedback loops

## 🏗️ Pipeline Architecture

*(Note: Add an image of your n8n workflow canvas here, or draw a quick flowchart in Excalidraw!)*

1. **Phase 1 (Aggregation):** Fetches daily posts, cleans HTML, removes duplicates, and filters out low-quality/non-technical content.
2. **Phase 2 (Topic Selection):** AI evaluates all articles and scores them based on virality and technical depth to pick a single "winning" topic.
3. **Phase 3 (Deep Research):** AI extracts core concepts, code examples, common mistakes, and use cases to prevent hallucinations in the final script.
4. **Phase 4 (Generation):** A specialized prompt transforms the research into a highly engaging YouTube script, which is then broken down into distinct JSON "scenes".
5. **Phase 5 (Rendering & Upload):** The JSON scenes are bundled and sent to external rendering APIs, and the final `.mp4` is automatically published to YouTube with AI-generated SEO tags.

---


---

# 🔄 Workflow Overview

```text
Schedule Trigger
        │
        ▼
Collect Trending Topics
        │
        ▼
Merge & Remove Duplicates
        │
        ▼
AI Topic Ranking
        │
        ▼
Quality Check
   ├── No → Find another topic
   └── Yes
        │
        ▼
Research Topic
        │
        ▼
Generate Script
        │
        ▼
Generate SEO
(Title • Description • Tags)
        │
        ▼
Generate Thumbnail Prompt
        │
        ▼
Generate Voice
        │
        ▼
Generate Images
        │
        ▼
Generate Captions
        │
        ▼
Render Video
        │
        ▼
Video Quality Check
   ├── Fail → Regenerate Script
   └── Pass
        │
        ▼
Upload to YouTube
        │
        ▼
Store Metadata
        │
        ▼
Notification
```
---

## 🛠️ Tech Stack

- **Orchestration:** n8n
- **LLMs:** Groq API (LLaMA 3.1 8B, Qwen 2.5 27B)
- **Scripting:** JavaScript (ES6+), Regex
- **Media APIs:** JSON2Video, ElevenLabs, Pollinations.ai

---

---

# 🚀 How It Works

### 1. Discover Trending Topics

The workflow gathers content from multiple free sources, including:

- GitHub Trending
- Dev.to
- Hashnode
- Reddit
- Hacker News
- RSS Feeds
- Official Documentation

Topics are merged, deduplicated, and ranked based on relevance.

---

### 2. Research

Once a topic is selected, the workflow collects information from trusted sources such as:

- Official documentation
- GitHub repositories
- Technical blogs
- Community discussions

The collected information is organized into a structured research document.

---

### 3. Content Generation

Using the research data, the workflow automatically generates:

- Video Script
- YouTube Title
- Description
- Tags
- Thumbnail Prompt

---

### 4. Media Generation

The workflow creates:

- AI Voiceover
- Images / Screenshots
- Captions
- Final Video

---

### 5. Quality Validation

Before publishing, the workflow verifies:

- Script quality
- Video completeness
- Rendering success

If validation fails, the workflow automatically returns to the content generation stage and regenerates the required assets.

---

### 6. Publishing

After successful validation, the workflow:

- Uploads the video to YouTube
- Stores video metadata
- Sends a completion notification

---


# 🔄 Feedback Loops

### 📌 Topic Validation

If a topic does not meet the required quality threshold, it is discarded and a new topic is selected automatically.

### 📌 Video Validation

If the rendered video fails validation, the workflow regenerates the script and media before attempting another render.

---

## 📁 Repository Contents

- `workflow.json`: The complete, exportable n8n pipeline containing all 44 nodes, routing logic, and custom JavaScript middleware.
- `json2video_demo_script.json`: A sample JSON payload generated by the AI to demonstrate the structural output sent to the video rendering engine.
- `custom_json_parser.js`: The standalone regex state-machine used to sanitize LLM hallucinations (extracted for visibility).

---

## 🚀 How to Run Locally

1. Install [n8n](https://n8n.io/).
2. In your n8n dashboard, click **Import from File** and upload `workflow.json`.
3. Add your API credentials for:
   - Groq API
   - JSON2Video API
   - ElevenLabs API (Optional, if not using JSON2Video's built-in TTS)
4. Click **Execute Workflow** to run a manual test, or activate the workflow to run on its daily schedule.


# 🚀 Getting Started

1. Read **ARCHITECTURE.md** to understand the complete workflow.
2. Build the workflow in **n8n** or import your own workflow JSON.
3. Configure the required credentials for external services.
4. Test the workflow manually.
5. Enable the schedule trigger for full automation.

---

# 📌 Project Status

> 🚧 **Work in Progress**

The architecture and workflow design are complete. Implementation is currently in progress.
