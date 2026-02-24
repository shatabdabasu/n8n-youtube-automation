
This assignment was implemented **entirely using free-tier resources**.

- The video is generated from a **basic, raw prompt** (no advanced fine-tuning or premium models).
- The end-to-end workflow is **fully automated**.
- Once the form input is submitted, the video is:
  - generated,
  - processed,
  - and **uploaded automatically to YouTube**
- **No manual intervention** is involved at any stage after submission.

The focus of this assignment is on **automation design, workflow orchestration, and correct integration of AI services**, not on video quality or premium tooling.


# 🎬 Automated YouTube Shorts Generation Pipeline (n8n)

This project demonstrates an **end-to-end AI-powered automation workflow** built using **n8n**, designed to generate, process, and publish YouTube Shorts with minimal manual intervention.

The workflow was created as part of an **assignment** to showcase practical understanding of:
- AI agents
- LLM integration
- API orchestration
- Media generation pipelines
- Automation-first system design

---

## 🧠 What This Workflow Does

From a single user input, the system:

1. Collects creative intent via a form
2. Converts intent into a **cinematic, policy-safe video prompt**
3. Generates **YouTube Shorts metadata** (title, description, hashtags)
4. Creates an AI-generated video using a text-to-video API
5. Downloads the generated video
6. Uploads the final video directly to YouTube with metadata applied

All steps are fully automated and orchestrated inside **n8n**.

---

## 🧩 High-Level Architecture

**Flow Overview:**
Form Input
↓
AI Agent (Prompt Generator)
↓
LLM (Google Gemini)
↓
Metadata Generator (JSON)
↓
Text-to-Video API
↓
Polling & Download
↓
Merge Video + Metadata
↓
YouTube Upload


---

## 🔧 Key Components

### 1. Form Trigger
- Collects user intent (e.g. *“How should the video be?”*)
- Acts as the entry point of the workflow

### 2. AI Agent (LangChain Agent Node)
- Converts user intent into a **single high-quality cinematic prompt**
- Enforces strict constraints:
  - Realistic, cinematic visuals
  - Vertical (9:16) YouTube Shorts format
  - Policy-safe, non-violent, non-cartoon style
  - Prompt-only output (no explanations)

### 3. Google Gemini (LLM)
- Used in two stages:
  - Prompt refinement
  - Strict JSON metadata generation (title, description, hashtags)

### 4. Text-to-Video API
- Sends the generated prompt to an external AI video generation service
- Handles async job creation and status polling
- Retrieves the final video URL once generation is complete

### 5. Video Download & Merge
- Downloads the generated video file
- Merges video output with generated metadata

### 6. YouTube Upload
- Uploads the video directly to YouTube
- Applies:
  - Title
  - Description
  - Tags
  - Category
  - Privacy settings

---

## 📦 Output

Each successful execution produces:
- A short-form AI-generated video (MP4)
- SEO-ready YouTube metadata
- A fully published YouTube Short (public)

---

## 🔐 Credentials & Security

- **No API keys or secrets are hard-coded**
- All credentials are managed via n8n’s credential system
- This repository/workflow is safe to share for academic and demonstration purposes

> Note: Users cloning this workflow must provide their own API keys and OAuth credentials.

---

## 🎓 Assignment Context

This workflow was built as part of an **educational assignment** to demonstrate:
- Practical automation skills
- Correct use of AI agents vs LLM calls
- API integration and async job handling
- Real-world media automation use cases

The inclusion of successful execution data is intentional to prove correctness and completeness.

---

## 🚀 Skills Demonstrated

- n8n workflow design
- LangChain agent usage
- LLM prompt engineering
- JSON-constrained AI outputs
- REST API orchestration
- Async job polling
- Media handling and publishing automation

---

## 📌 Notes

- The workflow is modular and extensible
- Additional platforms (Instagram Reels, TikTok) can be added with minimal changes
- Error handling and retries can be enhanced for production use

---

## ✅ Conclusion

This project demonstrates how **AI agents + LLMs + automation tools** can be combined to build a fully functional, real-world content pipeline — moving beyond prompt experimentation into **operational systems**.
