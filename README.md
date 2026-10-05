# 📞 Telugu AI Voice Receptionist

> **AI-powered healthcare voice receptionist for natural Telugu + English conversations**

A production-style conversational AI voice agent designed for healthcare appointment booking. It understands natural **Telugu + English code-mixed speech**, identifies the appropriate medical specialty based on symptoms, checks real-time doctor availability, books appointments after caller confirmation, and automatically logs call details.

---

## 🚀 Key Features

- 🎙️ **Natural Telugu + English conversations**
  - Understands code-mixed Telugu and English speech.
  - Designed for natural conversational interaction rather than literal translation.

- 🩺 **Symptom-to-specialty matching**
  - Identifies the caller's symptoms.
  - Suggests the appropriate medical specialty.

- 📅 **Real-time appointment availability**
  - Checks actual doctor availability through Google Calendar.
  - Offers available appointment slots to the caller.

- ✅ **Confirmation-based booking**
  - Books an appointment only after explicit caller confirmation.
  - Does not claim a booking was successful unless the booking actually succeeds.

- 🚨 **Emergency handling**
  - Detects potentially serious symptoms.
  - Provides appropriate emergency guidance.
  - Does not provide medical diagnosis or medical advice.

- 📊 **Automatic call logging**
  - Stores call transcripts.
  - Records call duration and outcome.
  - Maintains appointment and call information automatically.

- 🖥️ **Live client dashboard**
  - Clinic staff can view appointments and call information.
  - Data is automatically updated through Airtable.

---

## 🏗️ Architecture

```text
                    ┌─────────────────┐
                    │     Caller      │
                    │  Telugu/English │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │      Bolna      │
                    │    Voice AI     │
                    │                 │
                    │ Sarvam STT/TTS  │
                    │      + LLM      │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ Custom Webhook  │
                    │     Tools       │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │       n8n       │
                    │ Automation      │
                    │    Backend      │
                    └───────┬─┬───────┘
                            │ │
                ┌───────────┘ └───────────┐
                ▼                         ▼
       ┌─────────────────┐       ┌─────────────────┐
       │ Google Calendar │       │    Airtable     │
       │   Availability  │       │ Calls + Booking │
       │   & Booking     │       │      Logs       │
       └─────────────────┘       └────────┬────────┘
                                          │
                                          ▼
                                 ┌─────────────────┐
                                 │ Client Dashboard│
                                 └─────────────────┘
