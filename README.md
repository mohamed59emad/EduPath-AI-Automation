# 🚀 EduPath AI - Automated Educational Recommendation System

An end-to-end AI-powered automation system that generates personalized educational roadmaps and course recommendations for students based on their skills, goals, and interests, delivering them seamlessly via **WhatsApp** and **Email**.

---

## 🌟 Features

* **Instant Student Onboarding:** Collects user skills, education levels, and goals via custom forms.
* **Email Verification (OTP):** Generates and sends a secure 5-digit verification code using JavaScript & Gmail API.
* **Conditional Logic & Security:** Ensures only verified students proceed through the pipeline using IF condition handling.
* **Database Management:** Automatically logs student data and timestamps into Google Sheets.
* **AI Recommendation Engine:** Leverages **Google Gemini AI** to generate structured, personalized learning paths.
* **Multi-Channel Delivery:** Delivers recommendations instantly via **Meta WhatsApp Cloud API** and backup email notifications.

---
System Architecture :

[ 1. Student Submission ]
         │ (On form submission)
         ▼
[ 2. OTP Generation ]
         │ (Code in JavaScript)
         ▼
[ 3. Send Verification ]
         │ (Gmail: Send OTP)
         ▼
[ 4. Student Verification ]
         │ (Form: Next Form Page)
         ▼
[ 5. Decision Check (If Condition) ]
        ├── ❌ Incorrect OTP ──► [ Send Error Mail ]
        │
        └── 🟢 Correct OTP 
                  │
                  ▼
         [ 6. Data Cleaning & Format ] (Edit Fields)
                  │
                  ▼
         [ 7. Database Logging ] (Google Sheets: Append Row)
                  │
                  ▼
         [ 8. AI Recommendations ] (Google Gemini: Message Model)
                  │
                  ├──► [ 9a. Backup Email ] (Gmail: Send Recommendations)
                  └──► [ 9b. Instant Delivery ] (WhatsApp API: Send Message)

```text
[ Form Submission ] ──► [ Generate OTP ] ──► [ Send Email OTP ]
                                                   │
                                                   ▼
[ WhatsApp Message ] ◄── [ Google Gemini AI ] ◄── [ Google Sheets ] ◄── [ Verify OTP (IF) ]
