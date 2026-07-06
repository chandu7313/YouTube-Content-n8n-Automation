# 🚀 YouTube AI Automation

An **AI-powered YouTube automation workflow** built with **n8n** that automatically discovers trending software engineering topics, researches them, generates high-quality educational videos, and publishes them to YouTube.

The goal is to automate the complete content creation pipeline while maintaining quality through automated validation and feedback loops.

---

## 📖 Documentation

- **Architecture:** [`ARCHITECTURE.md`](ARCHITECTURE.md)
- **Printable Documentation:** [`docs/YouTube-AI-Automation-Architecture.pdf`](docs/YouTube-AI-Automation-Architecture.pdf)

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

# 🛠 Requirements

- n8n (Cloud or Self-hosted)
- AI Model (OpenAI, Ollama, Claude, etc.)
- Text-to-Speech Service
- Image Generation Service
- FFmpeg
- YouTube Data API (OAuth2)

---

# 📁 Repository Structure

```text
YouTube-AI-Automation/
│
├── README.md
├── ARCHITECTURE.md
└── docs/
    └── YouTube-AI-Automation-Architecture.pdf
```

---

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
