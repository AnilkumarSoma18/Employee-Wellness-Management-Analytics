# Mood Mentor — Employee Wellness Management Analytics

## Milestone 3: Emotion Detection & Wellness Intelligence

Mood Mentor is an AI-powered Employee Wellness Management Analytics system designed to analyze employee feedback, identify emotions and sentiment, and provide personalized wellness support.

### Key Features

- Multilingual employee feedback and journal analysis
- Automatic language detection and NLP preprocessing
- Text cleaning, tokenization, stopword removal, translation, and lemmatization
- Sentiment analysis using VADER
- Emotion detection using BERT and GoEmotions
- Emotion categories: Happy, Sad, Stress, Angry, Fear, and Neutral
- CSV and TXT feedback analysis
- AI-powered wellness chatbot using Qwen
- Facial emotion detection using DeepFace, OpenCV, and MTCNN
- Personalized wellness recommendations
- Employee mood history and mood tracking
- Mood calendar, trends, and emotion analytics
- Employee wellness dashboard
- PDF wellness reports
- PostgreSQL database integration
- JWT authentication and OTP verification
- FastAPI backend with Streamlit interface

### Emotion Detection Pipeline

```text
Employee Feedback
       ↓
Language Detection
       ↓
Text Cleaning & Preprocessing
       ↓
Tokenization & Stopword Removal
       ↓
Translation & Lemmatization
       ↓
Sentiment Analysis
       ↓
BERT Emotion Detection
       ↓
Wellness Recommendation
       ↓
PostgreSQL
       ↓
Dashboard & Reports
```

### Technologies Used

| Component | Technology |
|---|---|
| Programming Language | Python |
| Frontend | Streamlit |
| Backend | FastAPI, Uvicorn |
| Database | PostgreSQL |
| NLP | spaCy, LangDetect, VADER |
| Emotion Detection | BERT, GoEmotions |
| Generative AI | Qwen2.5 |
| Facial Emotion | DeepFace, OpenCV, MTCNN |
| Authentication | JWT, bcrypt, OTP |
| Reports | ReportLab |
| Environment | Google Colab, ngrok |

### Backend API

```text
GET  /health
POST /upload
POST /analyze
POST /analyze-text
POST /chat
```

### Project Structure

```text
Milestone3/
│
├── Emotion_Detection.ipynb
├── backend/
├── frontend/
├── screenshots/
└── README.md
```

### Execution

Start the FastAPI backend:

```bash
uvicorn backend:app --host 0.0.0.0 --port 8000
```

Start the Streamlit application:

```bash
streamlit run app.py --server.port 8501
```

### Milestone 3 Outcome

Milestone 3 implements the core emotion intelligence layer of Mood Mentor by combining multilingual NLP, sentiment analysis, BERT-based emotion detection, facial emotion detection, AI wellness conversation, personalized recommendations, mood tracking, dashboards, and wellness reporting.

