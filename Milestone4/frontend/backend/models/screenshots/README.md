# 🌿 Mood Mentor — Employee Wellness Management Analytics

## 🚀 Milestone 4 — Integrated Wellness Platform

**Mood Mentor** is an AI-powered Employee Wellness Management Analytics application that combines emotion intelligence, multilingual NLP, wellness recommendations, mood tracking, AI-assisted conversations, facial emotion detection, secure authentication, and employee/manager analytics into one integrated platform.

> **Milestone 4 focus:** Production-style integration of the complete wellness workflow with Streamlit, FastAPI, PostgreSQL, AI/NLP models, authentication, reporting, and deployment support.

---

## ✨ What This Milestone Provides

- 🧠 Multilingual employee feedback and journal analysis
- 😊 Emotion detection with **BERT / GoEmotions**
- 💭 Sentiment analysis using **VADER**
- 🌐 Automatic language detection and translation
- 📝 Text preprocessing, tokenization, stopword filtering, and lemmatization
- 🤖 AI Wellness Chat using **Qwen2.5-0.5B-Instruct**
- 📷 Facial emotion detection using **DeepFace, OpenCV, and MTCNN**
- 💡 Confidence-based wellness recommendations
- 📊 Employee mood history, trends, calendar, and analytics
- 👥 Employee and Manager roles
- 🔐 JWT authentication, password hashing, email verification, and OTP
- 🗄️ PostgreSQL persistence
- 📄 PDF wellness reports
- ⚡ FastAPI backend APIs
- 🎨 Streamlit user interface
- 🌍 Google Colab + ngrok deployment/testing workflow

---

## 🧩 System Architecture

```text
                    ┌─────────────────────┐
                    │      Employee       │
                    └──────────┬──────────┘
                               │
             ┌─────────────────┼─────────────────┐
             │                 │                 │
             ▼                 ▼                 ▼
        Journal/Text      Face Detection     Mood Entry
             │                 │                 │
             ▼                 ▼                 │
       Multilingual NLP      DeepFace           │
             │                 │                 │
             ├───────┬─────────┘                 │
             ▼       ▼                           │
          VADER    BERT/GoEmotions               │
             │       │                           │
             └───────┼───────────────────────────┘
                     ▼
             Emotion + Sentiment
                     │
                     ▼
          Wellness Recommendation
                     │
                     ▼
              PostgreSQL DB
                     │
          ┌──────────┴──────────┐
          ▼                     ▼
   Employee Dashboard      Manager Reports
          │                     │
          └──────────┬──────────┘
                     ▼
                PDF Reports
```

---

## 🧠 AI & NLP Pipeline

```text
Input
  ↓
Language Detection
  ↓
Normalization & Cleaning
  ↓
Tokenization
  ↓
Stopword Filtering
  ↓
Translation to English
  ↓
Lemmatization
  ↓
VADER Sentiment Analysis
  ↓
BERT Emotion Classification
  ↓
Emotion Mapping
  ↓
Confidence Analysis
  ↓
Wellness Recommendation
  ↓
Database Storage
  ↓
Dashboard / Reports
```

### Emotion Categories

```text
😊 Happy
😐 Neutral
😢 Sad
😫 Stress
😠 Angry
😨 Fear
```

The BERT/GoEmotions output is mapped into these application-level categories.

---

## 🤖 Wellness Intelligence

The recommendation engine combines emotion and sentiment information to generate wellness guidance.

Confidence levels are handled as:

```text
< 0.40       → Low
0.40 – 0.69  → Medium
≥ 0.70       → High
```

Recommendations become more structured when a negative emotional signal has higher confidence.

---

## 💬 AI Wellness Chat

The wellness chatbot uses:

```text
Qwen/Qwen2.5-0.5B-Instruct
```

It supports:

- Supportive wellness conversations
- Recent conversation history
- General coping suggestions
- Employee wellness guidance
- Crisis-language detection and safety handling

The chatbot is intended for wellness support and does not provide medical diagnosis.

---

## 📷 Facial Emotion Detection

The Face Detection module uses:

```text
DeepFace
OpenCV
MTCNN
```

Users can provide an image through camera capture or upload an image. The system analyzes the detected facial emotion, confidence, and stores the result as a mood record.

---

## 🔐 Authentication & User Management

The application includes:

- User registration
- Secure password hashing with bcrypt
- JWT authentication
- Email verification
- OTP generation and verification
- Password reset
- Employee role
- Manager role
- Protected backend APIs

OTP codes expire after **10 minutes**, while JWT authentication uses an expiry configured for the application.

---

## 🗄️ Database

PostgreSQL is used as the persistent data layer.

### Main Data

```text
users
├── username
├── email
├── password hash
├── verification status
└── role

otp_codes
├── email
├── code
├── purpose
├── expiry
└── used status

mood_logs
├── user
├── mood date
├── sentiment
├── emotion
├── compound score
├── confidence
├── journal text
├── source
└── created timestamp
```

Mood records can originate from:

```text
manual
nlp
face
```

---

## ⚡ FastAPI Backend

The backend is implemented using **FastAPI**.

### API Endpoints

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/health` | Backend health check |
| POST | `/upload` | Upload CSV/TXT feedback |
| POST | `/analyze` | Analyze uploaded feedback |
| POST | `/analyze-text` | Analyze typed journal text |
| POST | `/chat` | Wellness chatbot |

The backend validates JWT authorization for protected operations.

---

## 📊 Analytics & Reporting

The platform provides:

### Employee Analytics

- Current mood
- Mood history
- Mood calendar
- Mood distribution
- Mood trends
- Emotion confidence
- Recent activity
- Wellness recommendations

### Manager Analytics

- Employee mood information
- Latest employee mood
- Employee wellness data
- Recent mood records
- Reporting functionality

### PDF Reports

Reports can contain:

- Employee information
- Selected date range
- Mood summary
- Wellness recommendation
- Mood entries
- Emotion
- Confidence
- Data source

---

## 🛠️ Technology Stack

| Layer | Technology |
|---|---|
| Language | Python |
| UI | Streamlit |
| API | FastAPI |
| Server | Uvicorn |
| Database | PostgreSQL |
| NLP | spaCy, LangDetect, FTFY, Emoji |
| Translation | Deep Translator |
| Sentiment | VADER |
| Emotion AI | BERT, GoEmotions |
| Generative AI | Qwen2.5 |
| Face AI | DeepFace, OpenCV, MTCNN |
| ML | PyTorch, Transformers |
| Authentication | JWT, bcrypt, OTP |
| Data | Pandas |
| Visualization | Matplotlib |
| Reporting | ReportLab |
| Runtime / Testing | Google Colab |
| Public Tunnel | ngrok |

---

## 📁 Milestone 4 Structure

```text
Milestone4/
│
├── ani.ipynb
├── backend/
│   ├── backend.py
│   ├── db.py
│   ├── auth.py
│   ├── email_utils.py
│   ├── nlp_pipeline.py
│   └── recommendations.py
│
├── frontend/
│   └── app.py
│
├── screenshots/
│   ├── Dashboard.png
│   ├── Face Detection.png
│   ├── Home.png
│   ├── Journal.png
│   ├── Login.png
│   ├── Relax.png
│   └── Wellness Chat.png
│
└── README.md
```

---

## ▶️ Running the Application

### 1. Install Dependencies

```bash
pip install streamlit psycopg2-binary PyJWT bcrypt python-dotenv email-validator pyngrok fastapi uvicorn python-multipart requests langdetect ftfy emoji deep-translator vaderSentiment spacy pandas matplotlib transformers accelerate torch stopwordsiso deepface tf-keras opencv-python-headless mtcnn reportlab
```

Install the multilingual spaCy model:

```bash
python -m spacy download xx_sent_ud_sm
```

### 2. Configure Environment Variables

Create a `.env` file with your database, authentication, SMTP, and other required configuration values.

**Never upload real passwords, JWT secrets, SMTP app passwords, or ngrok tokens to GitHub.**

### 3. Start FastAPI

```bash
uvicorn backend:app --host 0.0.0.0 --port 8000
```

### 4. Start Streamlit

```bash
streamlit run app.py --server.port 8501
```

### 5. Optional Google Colab + ngrok

The notebook also provides a workflow to launch FastAPI and Streamlit together and expose the Streamlit application through ngrok.

---

## 🔄 Complete User Workflow

```text
Register / Login
       ↓
Email / OTP Verification
       ↓
Employee Dashboard
       ↓
Choose Wellness Feature
       │
       ├── Manual Mood
       ├── Journal Analysis
       ├── CSV/TXT Analysis
       ├── Wellness Chat
       ├── Face Detection
       └── Relax
       ↓
AI / NLP Processing
       ↓
Emotion + Sentiment
       ↓
Wellness Recommendation
       ↓
PostgreSQL Storage
       ↓
Mood Analytics
       ↓
Dashboard / Manager Reports
       ↓
PDF Export
```

---

## 🎯 Milestone 4 Outcome

Milestone 4 brings the major Mood Mentor components together into a single integrated Employee Wellness Management Analytics platform.

It connects **AI emotion detection, multilingual NLP, sentiment analysis, facial emotion recognition, wellness recommendations, conversational AI, secure authentication, PostgreSQL storage, analytics, reporting, and Streamlit/FastAPI deployment** into one complete workflow.

### 🌿 Mood Mentor

**Understand emotions. Track wellness. Support better workplaces.**

> Built with Python • AI/ML • NLP • FastAPI • Streamlit • PostgreSQL
