# 📚 Multimodal AI Chat – Chat with PDF, YouTube & Local Videos

A Streamlit-based AI application that allows you to **chat with PDFs**, **ask questions about YouTube videos**, and **analyze local video files** using **Google Gemini AI**, **LangChain**, and **FAISS**.

---

## 🚀 Features

- **PDF Chat:**
  - Upload a PDF.
  - Extract and index text using FAISS.
  - Ask questions about the PDF content.
  
- **YouTube Chat:**
  - Provide a YouTube URL.
  - Fetch transcripts automatically.
  - Ask questions about the video content.

- **Local Video Analysis:**
  - Upload a video file.
  - AI analyzes the video content using Gemini (multimodal model).
  - Supports insights + additional web-based context (DuckDuckGo).

- **Multilingual Support:**
  - Detects any language input.
  - Translates queries to English for processing.
  - Translates answers back to the user's language.

- **Text-to-Speech:**
  - Converts AI responses into audio.
  - Plays within the app.

---

## 🛠️ Tech Stack

- **Frontend:** [Streamlit](https://streamlit.io/)
- **AI Models:** Google Gemini (`gemini-pro`, `gemini-2.0-flash-exp`)
- **Libraries Used:**
  - `langchain`, `FAISS`, `PyPDF2`
  - `YouTubeTranscriptApi`
  - `gTTS` for text-to-speech
  - `googletrans`, `langdetect`
  - `phi.agent` for multimodal video understanding
- **Cloud AI:** [Google Generative AI API](https://ai.google.dev/)

---

## ⚙️ How It Works (Step by Step)

### 1) **PDF Mode**
1. Upload a PDF file.
2. Extract and chunk text.
3. Generate embeddings using Google Generative AI.
4. Store vectors in FAISS.
5. Ask a question → FAISS retrieves relevant context → Gemini answers.

### 2) **YouTube Mode**
1. Paste YouTube URL.
2. Extract video transcript.
3. Index transcript in FAISS.
4. Ask a question → Retrieve relevant transcript chunks → Gemini answers.

### 3) **Local Video Mode**
1. Upload video file.
2. File is processed and uploaded to Gemini.
3. AI analyzes the video content.
4. Answers user queries using video insights + optional web lookups.

### **Language & TTS Pipeline**
- Detect query language.
- Translate to English if not already.
- AI processes and generates an English response.
- Translate back to the original language.
- Convert answer to speech (MP3) and play.

---

## 🏗️ System Architecture

```mermaid
flowchart TD
    A[User Uploads PDF / YouTube URL / Video] --> B[Extract Text / Transcript / Video Frames]
    B --> C[Split Text into Chunks]
    C --> D[Generate Embeddings with Google Generative AI]
    D --> E[Store/Load in FAISS Vector Database]
    E --> F[User Asks a Question]
    F --> G[Detect & Translate Language]
    G --> H[Retrieve Relevant Context from FAISS or Analyze Video]
    H --> I[Gemini Model Generates Answer]
    I --> J[Translate Answer Back]
    J --> K[Convert to Speech (gTTS)]
    K --> L[Display & Play Answer]
