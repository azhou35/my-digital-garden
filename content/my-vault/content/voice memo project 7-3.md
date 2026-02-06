---
title: "voice memo project 7-3"
---

# 🎙️ Voice Memo Journal – Product Requirements Document (PRD)

## 🧭 Overview

**Product Name:** Voice Memo Journal  
**Type:** Mobile-friendly voice journaling tool  
**Goal:** Enable users to record, transcribe, tag, and review voice memos with minimal friction — while building technical fluency in full-stack prototyping.

---

## 🧠 Problem

Voice memos are a powerful medium for self-reflection, ideation, and journaling. But most workflows require manual transcription and lack structured organization. Current tools are not:

- Mobile-native  
- Transcription-capable  
- Taggable or searchable  
- Fun or lightweight to use  

---

## 🎯 Objectives

- Record or upload voice memos easily (especially on mobile)  
- Auto-transcribe using Whisper  
- Store and organize entries with timestamp + optional metadata (mood, theme)  
- View and search transcripts over time  
- Be fully owned, hackable, and extensible by the builder (you!)  

---

## 👤 Target User

- People who journal using audio (e.g. daily check-ins, voice ideation)  
- Builders prototyping voice-based interfaces  
- Technically inclined users wanting privacy + control  

---

## 🧱 Core Features (MVP)

| Feature | Description |
|--------|-------------|
| 🎤 Audio upload | Upload `.wav` or `.mp3` files via mobile or desktop browser |
| 📝 Transcription | Transcribe using OpenAI Whisper (base model for speed) |
| 🕓 Timestamped storage | Store with filename, transcript, and datetime |
| 🧠 Simple UI | Upload, view entries, browse transcripts |
| 🗂️ SQLite database | Lightweight local storage for prototyping |

---

## 💡 Future Features (Post-MVP)

- Manual or automatic **mood tagging**  
- **Sentiment analysis** with OpenAI or Hugging Face  
- Search / filter by tag, keyword, time  
- Export to Notion or Airtable  
- Audio recording directly from browser (or shortcut)  
- Visualizations (timeline, mood charts)  

---

## 🧪 Technical Architecture

### 📐 High-Level System

```
[User uploads voice memo]
        ⬇️
[Flask server receives file]
        ⬇️
[Whisper transcribes audio]
        ⬇️
[Transcript stored in SQLite DB]
        ⬇️
[Web UI shows list of entries]
```

---

## 🔧 Tech Stack

| Layer | Technology | Notes |
|-------|------------|-------|
| **Backend** | Flask (Python) | Lightweight web server |
| **Transcription** | `openai-whisper` (local) | No API needed, runs locally |
| **Database** | SQLite | No setup required |
| **Frontend** | HTML/CSS (Jinja templating) | Minimal mobile-first layout |
| **Styling** | Custom CSS | Clean and lightweight |
| **Audio Handling** | Python `werkzeug` file utils | Secure audio upload |

---

## 🗂️ Project Structure

```
voice-memo-app/
├── app.py              # Flask app
├── transcriber.py      # Whisper transcription logic
├── db.py               # SQLite helpers
├── templates/
│   └── index.html      # UI
├── static/
│   └── style.css       # Basic CSS
├── recordings/         # Uploaded audio files
├── transcripts.db      # SQLite DB file
├── requirements.txt    # Python dependencies
```

---

## 🧪 Key Files Breakdown

### `app.py`

- Handles web routes:  
  - `GET /` shows all transcripts  
  - `POST /` handles audio upload, triggers transcription  
- Stores files in `recordings/`  
- Saves results in SQLite via `db.py`  

### `transcriber.py`

- Loads Whisper base model  
- Converts `.wav` or `.mp3` into text  
- Returns full transcript  

### `db.py`

- Initializes database (if not exists)  
- Provides functions to save and retrieve entries  
- Fields: `id`, `filename`, `transcript`, `timestamp`  

### `index.html`

- Upload form for audio  
- List of past transcripts with timestamps  

### `style.css`

- Responsive mobile styling  
- Simple layout and font choices  

---

## ✅ Setup Instructions

```bash
pip install -r requirements.txt
python app.py
```

Then go to [http://localhost:5000](http://localhost:5000)

---

## 📱 Mobile Integration Notes

- Audio recorded on iPhone or Android can be shared/uploaded from browser  
- Optionally integrate with:  
  - iOS Shortcuts → HTTP POST to Flask  
  - Android Tasker → file upload  
- Later: Enable browser-based recording with JavaScript  

---

## 🔄 Future Extensions

- Add OpenAI sentiment tagging  
- Migrate to Supabase for sync across devices  
- Use Streamlit/React for richer UI  
- Visualize patterns: when you record, what moods, word usage  
- Add local authentication / encryption for privacy