\# Telugu AI Voice Receptionist



A production-style conversational AI voice agent for healthcare appointment 

booking, built for natural Telugu + English code-mixed conversation. The agent 

answers calls, matches caller symptoms to the right specialty, checks real-time 

doctor availability, books appointments, and logs everything automatically.



\## Architecture



Caller → Bolna (voice AI: Sarvam STT/TTS + LLM) → Custom webhook tools → 

n8n (automation backend) → Google Calendar + Airtable → Client dashboard



\## What it does



\- Understands natural Telugu/English mixed speech, not just literal translation

\- Matches symptoms to the correct specialty and proactively offers real available slots

\- Books appointments only after explicit caller confirmation — never fabricates 

&#x20; a successful booking

\- Escalates to emergency guidance for serious symptoms, refuses medical advice

\- Logs every call's transcript, duration, and outcome automatically

\- Surfaces a live, auto-updating dashboard for clinic staff



\## Stack



\- \*\*Voice AI platform:\*\* Bolna (Sarvam Bulbul v3 TTS, saaras:v3 STT, Azure GPT-4.1-mini)

\- \*\*Automation backend:\*\* n8n (self-hosted, Docker)

\- \*\*Calendar integration:\*\* Google Calendar API

\- \*\*Data store / dashboard:\*\* Airtable (bookings + call logs, shared live views)



\## Repo contents



\- `n8n-workflows/` — exported automation workflows (availability check, booking, call logging)

\- `prompts/canvas-system-prompt.md` — the full conversational behavior prompt

\- `docs/architecture.md` — data flow explanation

