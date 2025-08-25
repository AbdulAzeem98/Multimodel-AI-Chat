#Multimodal AI Chat – PDF, YouTube & Video

A Streamlit app that lets you chat with PDFs, YouTube videos, and local video files using Google Gemini AI and LangChain.

->Key Features

-Upload PDF → extract & index text.
-Paste YouTube link → fetch transcript.
-Upload video → AI analyzes video content.
-Multilingual Q&A with auto-translate.
-Text-to-speech playback.

->How It Works (High Level)

1. Input: User uploads PDF/YouTube/video.
2. Extract: Text or transcript pulled (videos uploaded to Gemini).
3. Chunk & Embed: Split into chunks, generate embeddings with Gemini.
4. Store: Save embeddings in FAISS.
5. Ask: Detect/translate language, retrieve relevant chunks or video insights.
6. Generate Answer: Gemini produces context-aware answer.
7. Translate & Speak: Answer translated back and converted to speech.


->Architecture Flow

Input → Extract → Embed & Store (FAISS) → Retrieve & Generate (Gemini) → Translate → Display + Audio.

