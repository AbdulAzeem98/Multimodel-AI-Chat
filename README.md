Multimodal AI Chat – PDF, YouTube & Video

A Streamlit app that lets you chat with PDFs, YouTube videos, and local video files using Google Gemini AI and LangChain.

Key Features

-Upload PDF → extract & index text.
-Paste YouTube link → fetch transcript.
-Upload video → AI analyzes video content.
-Multilingual Q&A with auto-translate.
-Text-to-speech playback.

How It Works (High Level)

Input: User uploads PDF/YouTube/video.
Extract: Text or transcript pulled (videos uploaded to Gemini).
Chunk & Embed: Split into chunks, generate embeddings with Gemini.
Store: Save embeddings in FAISS.
Ask: Detect/translate language, retrieve relevant chunks or video insights.
Generate Answer: Gemini produces context-aware answer.
Translate & Speak: Answer translated back and converted to speech.


Architecture Flow

Input → Extract → Embed & Store (FAISS) → Retrieve & Generate (Gemini) → Translate → Display + Audio.

Architecture Flow

Input → Extract → Embed & Store (FAISS) → Retrieve & Generate (Gemini) → Translate → Display + Audio.
