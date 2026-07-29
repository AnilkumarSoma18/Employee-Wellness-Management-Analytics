# 🧠 Mood Mentor: Intelligent Employee Wellness Platform

Mood Mentor is an award-winning, full-stack, data-driven web application designed to monitor, analyze, and improve employee wellness using advanced Artificial Intelligence and Computer Vision. 

Wrapped in a stunning, modern **Glassmorphism UI**, Mood Mentor offers a seamless and highly interactive user experience.

## ✨ Key Features

*   **🔒 Secure Authentication:** Robust user login and registration system featuring Postgres-backed credentials, hashed passwords, and secure Email OTP verification.
*   **📊 Multilingual NLP Sentiment Analysis:** Upload CSV or TXT feedback files and let the FastAPI backend run advanced Natural Language Processing to detect the language, calculate sentiment scores (Positive, Negative, Neutral), and determine the dominant emotion using VADER. Includes downloadable PDF reports!
*   **📷 Advanced Biometric Face Analysis:** Uses state-of-the-art Deep Learning (MTCNN & DeepFace) combined with OpenCV to scan facial micro-expressions. It draws Sci-Fi-style tracking boxes directly onto the image and calculates a custom "Biometric Wellness Score".
*   **🤖 AI Wellness Assistant:** Powered by Google's Gemini 1.5 model, this AI acts as a personal mood mentor. The entire conversation history is safely persisted in the PostgreSQL database.
*   **📓 Smart AI Gratitude Journal:** A secure digital diary where users can log their thoughts. The AI instantly analyzes the text context to log the exact mood state.
*   **📈 Interactive Mood Analytics:** A dynamic, Plotly-powered dashboard that pulls historical emotional data from the Postgres database to map long-term wellness trends on a beautiful area chart.
*   **🎵 Smart Music Therapy & Breathing:** An interactive `Relax` module that fetches the user's most recent biometric or journal mood from the database and automatically curates a Spotify playlist to match their exact emotional needs (e.g., Acoustic for Stress, Pop for Happiness). Also features a CSS-animated 4-7-8 breathing exercise.

## 🛠️ Technology Stack

*   **Frontend:** Streamlit, HTML5, Custom CSS3 (Glassmorphism, CSS Animations)
*   **Backend:** FastAPI (Python)
*   **Database:** PostgreSQL (`psycopg2`)
*   **AI / Machine Learning:** 
    *   Google Gemini 1.5 Pro/Flash API (Chat Assistant)
    *   DeepFace & MTCNN (Facial Emotion Recognition)
    *   VADER Sentiment Analysis (NLP text processing)
    *   OpenCV (Computer Vision bounding boxes)
*   **Data Visualization:** Plotly
*   **Utilities:** `fpdf2` (PDF Generation), `smtplib` (Email OTPs)

## 🚀 Setup & Installation

### 1. Prerequisites
Ensure you have Python 3.9+ installed and a running instance of PostgreSQL. 

### 2. Install Dependencies
Install all required Python libraries:
```bash
pip install streamlit fastapi uvicorn psycopg2-binary python-dotenv requests fpdf2 plotly deepface mtcnn opencv-python-headless vaderSentiment
```

### 3. Environment Variables
Create a `.env` file in the root directory and add the following keys:
```env
# Database Credentials
DB_HOST=your_postgres_host
DB_PORT=5432
DB_NAME=your_db_name
DB_USER=your_db_user
DB_PASSWORD=your_db_password

# Email OTP Credentials
EMAIL_SENDER=your_email@gmail.com
EMAIL_PASSWORD=your_app_password

# Google Gemini API
GEMINI_API_KEY=your_gemini_api_key

# Backend URL
BACKEND_URL=http://localhost:8000
```

### 4. Run the Application
You will need to run both the FastAPI backend and the Streamlit frontend.

**Start the Backend:**
```bash
uvicorn backend_api:app --reload --port 8000
```

**Start the Frontend:**
```bash
streamlit run app.py
```

## 📂 Project Structure
```
├── app.py                     # Main Streamlit App (Login, NLP upload)
├── backend_api.py             # FastAPI Server (Handles NLP processing)
├── db.py                      # PostgreSQL Database Models & Queries
├── auth.py                    # Authentication & Security logic
├── email_utils.py             # Email OTP sender
├── nlp_pipeline.py            # VADER Sentiment & Language detection
├── pages/
│   ├── 1_Profile_Dashboard.py # Interactive Plotly Analytics
│   ├── 2_Face_Detection.py    # MTCNN Biometric Scanner
│   ├── 3_AI_Assistant.py      # Gemini Chatbot
│   ├── 4_Journal.py           # NLP Gratitude Journal
│   └── 5_Relax.py             # Dynamic Music & Breathing Therapy
└── README.md
```

## 🎨 Design Philosophy
Mood Mentor steps away from traditional, flat dashboards. It utilizes a custom CSS implementation of "Glassmorphism"—featuring semi-transparent frosted glass panels (`backdrop-filter: blur`), slow-moving vibrant gradient backgrounds, soft drop shadows, and subtle micro-animations (like smooth slide-up loading effects). This ensures the application feels like a premium, award-winning enterprise product.

---
*Built to improve workplace wellness through data and AI.*
