
# 🛡️ SafeSpot

SafeSpot is a mobile-first safety alert system designed to help users in Israel stay informed during security events by delivering **location-relevant alerts** using **AI-powered filtering**. The system reduces information overload and anxiety caused by irrelevant mass notifications during times of conflict or emergency.

[🎨 View SafeSpot Presentation on Canva](https://www.canva.com/design/DAGoQvT0tiE/JZDskXgmcS7eYfTEWJUPfA/view?utm_content=DAGoQvT0tiE&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=h0ac8c48732)

---

## 📍 Problem Statement

During security threats in Israel, citizens receive many mass-distributed alerts, often unrelated to their actual location. This leads to alert fatigue and decreased public responsiveness. SafeSpot solves this by delivering only **geographically-relevant alerts** in real time.

---

## 🚀 Solution Overview

SafeSpot aggregates security alerts from trusted RSS feeds, classifies them using **OpenAI GPT-4o-mini**, and filters them by user location. Key features:

- 📱 Mobile-first interface
- 📡 Real-time push notifications
- 🧠 AI-based classification of alerts
- 🌍 Location-aware filtering

---

## 🛠️ Core Technologies

- **Frontend**: React + TypeScript, Tailwind CSS, Capacitor
- **Backend**: Supabase (Edge Functions, PostgreSQL)
- **AI**: OpenAI GPT-4o-mini for natural language classification
- **Push Notifications**: Firebase Cloud Messaging (FCM)

---

## ⚙️ System Architecture

### Frontend
- React App with Capacitor
- Tailwind CSS for UI
- Firebase registration for push tokens

### Backend (Supabase)
- Auth & Session Management
- PostgreSQL with RLS
- Edge Functions:
  - `classify-alert`: AI-based alert classification
  - `send-notification`: Alert delivery
  - `chat-calm`: Chat support for user assistance

### External Services
- RSS feeds: Haaretz, Walla, Kan News, etc.
- CORS Proxy: api.allorigins.win

---

## 🧾 Database Design

Normalized schema with key tables:
- `alerts`, `profiles`, `rss_sources`
- `user_alert_history`, `notification_preferences`
- `user_rss_preferences`, `location_history`

Secured by **Row-Level Security (RLS)** for user privacy.

---

## 🧠 AI Classification Flow

1. New RSS alert is received.
2. Alert content is sent to GPT-4o-mini via Supabase Edge Function.
3. AI identifies if it's a security alert and extracts relevant location.
4. Fallback to keyword-based matching if AI fails.

---

## 📲 User Flows

- **Initial Setup**: Login → Location Permission → Source Preferences
- **Live Flow**: RSS Ingestion → AI Classification → Location Filtering → Push Delivery
- **User Controls**: View history, snooze alerts, override location

---

## 🔗 External Dependencies

- OpenAI API
- Firebase Cloud Messaging
- Supabase Edge Functions
- CORS Proxy
- Trusted RSS Sources

---

## 🧩 Summary

SafeSpot is a secure, intelligent, and user-focused alert companion that empowers people during emergencies by delivering **only what matters**, exactly when and where it’s needed.

---
