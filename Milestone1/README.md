# 🌿 Employee Wellness Management Analytics

## 📌 Project Overview

Employee Wellness Management Analytics, also known as **Mood Mentor**, is a secure and interactive wellness application developed using Python and Streamlit.

The platform provides secure user authentication and allows employees to check in with their current mood using seven interactive mood levels. Based on the selected mood, the application provides personalized wellness feedback, a wellness score, a visual progress indicator, and practical well-being recommendations.

The application also supports employee wellness CSV file uploads for future analytics and insights.

---

## 🎯 Project Objectives

The main objectives of this project are:

- Develop a secure employee authentication system
- Protect user passwords using encryption
- Provide OTP-based password recovery
- Support secure user sessions using JWT authentication
- Allow employees to record their current mood
- Generate personalized wellness feedback
- Promote employee well-being through daily recommendations
- Support employee wellness data uploads for future analytics

---

## ✨ Key Features

### 🔐 Secure User Authentication

- New user registration
- Secure user login
- Password confirmation and validation
- Password encryption using bcrypt
- JWT-based authentication
- Secure session management
- User logout functionality

### 📧 Forgot Password and OTP Verification

- Password recovery using a registered email address
- Six-digit OTP generation
- OTP delivery using Gmail SMTP
- OTP verification
- Secure password reset
- New password encryption before database storage

### 😊 Seven-Level Mood Check-In

Employees can select their current mood from seven interactive mood levels:

😭 Very Low  
😥 Low  
😟 Not Good  
😐 Neutral  
🙂 Good  
😊 Very Good  
🤩 Excellent  

The application provides personalized wellness feedback based on the selected mood.

### 💚 Wellness Dashboard

- Personalized employee welcome message
- Interactive mood selection
- Dynamic wellness score
- Visual wellness progress indicator
- Mood-based wellness feedback
- Daily self-care recommendations
- Employee wellness CSV file upload
- Secure logout option

### 🎨 Modern User Interface

- Light pastel color theme
- Soft gradient background
- Modern wellness cards
- Interactive mood emojis
- Smooth animations
- Responsive page layout
- Customized sidebar navigation
- Clean and user-friendly design

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Application development |
| Streamlit | Web application interface |
| Neon PostgreSQL | Cloud database |
| psycopg2 | PostgreSQL database connection |
| bcrypt | Password hashing and encryption |
| PyJWT | JWT authentication |
| Gmail SMTP | OTP email delivery |
| HTML | Custom interface components |
| CSS | Light theme, cards, styling, and animations |
| Google Colab | Development environment |

---

## 🗄️ Database

The application uses **Neon PostgreSQL**, a cloud-hosted PostgreSQL database.

The user table securely stores:

- User ID
- Name
- Email address
- Encrypted password

Passwords are encrypted using bcrypt before being stored. Plain-text passwords are not saved in the database.

---

## 🔄 Application Workflow

1. The user opens the Mood Mentor application.
2. A new user creates an account using the Sign Up page.
3. The password is encrypted using bcrypt.
4. User information is stored securely in Neon PostgreSQL.
5. The registered user logs in using an email address and password.
6. A JWT token is generated after successful authentication.
7. The authenticated user accesses the wellness dashboard.
8. The user selects one of the seven mood levels.
9. The application generates personalized wellness feedback.
10. A wellness score and visual progress indicator are displayed.
11. The application provides practical wellness recommendations.
12. The user can upload an employee wellness CSV file.
13. The user can securely log out.

---

## 🔑 Password-Recovery Workflow

1. The user opens the Forgot Password page.
2. The user enters the registered email address.
3. The application verifies the email in Neon PostgreSQL.
4. A random six-digit OTP is generated.
5. The OTP is sent using Gmail SMTP.
6. The user enters and verifies the OTP.
7. The user creates a new password.
8. The new password is encrypted using bcrypt.
9. The encrypted password is updated in the database.

---

## 🔒 Security Features

- bcrypt password hashing
- JWT-based authentication
- Password validation
- Secure session management
- OTP-based identity verification
- Registered-email validation
- PostgreSQL parameterized queries
- Protected dashboard access
- Hidden database credentials
- Hidden Gmail App Password
- Hidden JWT secret key

---

## 📂 Project Structure

```text
Employee-Wellness-Management-Analytics/
│
├── Authentication.ipynb
├── README.md
│
└── screenshots/
    ├── home_page.png
    ├── signup_page.png
    ├── login_page.png
    ├── forgot_password_page.png
    ├── dashboard.png
    └── neon_database.png