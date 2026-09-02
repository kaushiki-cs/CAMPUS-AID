# CampusAid — Emergency Safety Companion

**Built for IEEE PromptWars × WIE-IEEE — Build with AI: Assistive Health & Emergency Safety**

CampusAid is a multimodal AI safety companion for college campuses, powered by Google's Gemini API. It helps students act fast and stay calm in the critical first minutes of a campus emergency.

## Features

### 🩹 Report an Issue (Triage)
Describe a situation in plain language, or attach a photo. CampusAid assesses severity (urgent / moderate / mild) and returns a clear, step-by-step first-aid protocol — factoring in visual context from photos when provided.

### 🌐 Translate Warning
Paste safety warning text (or describe a sign), pick a language, and get an instant, plain-spoken translation. Supports Spanish, Mandarin Chinese, Hindi, Arabic, French, and Tagalog — so safety information isn't blocked by a language barrier.

### 📣 Emergency Contacts
One-tap alerts to designated contacts — ambulance (108), campus security, resident advisor, or a personal emergency contact — with the situation summary and last known location. Includes a live alert log.

## Tech Stack

- **Frontend:** Vanilla HTML/CSS/JavaScript, single-file app
- **AI:** Google Gemini API (`gemini-3.6-flash`) via the `generateContent` endpoint, using multimodal input (text + inline image data)
- **Auth:** Gemini Auth key (`x-goog-api-key` header)
- **Storage:** API key stored client-side only (`localStorage`) — never sent anywhere but Google's API
- **Hosting:** Netlify

## Setup

1. Open `campusaid.html` in a browser (or deploy it as a static site — no build step required).
2. Click **"Add Gemini API key"** in the top right.
3. Get a free key from [Google AI Studio](https://aistudio.google.com/apikey) and paste it in.
4. Start describing a situation, translating a warning, or exploring the emergency contacts tab.

## Design Notes

- **Graceful degradation:** if the live Gemini call fails (network issue, key problem, etc.), the app falls back to pre-written offline responses for common scenarios (fainting, gas leak, sprained ankle, seizure) so the guidance flow never breaks — clearly flagged with a "Demo mode" badge.
- **India-specific emergency numbers:** all guidance references 112 (national emergency helpline) and 108 (ambulance), never 911.
- **Not a medical device:** CampusAid explicitly states in every response that it is not a substitute for professional medical care, and prompts users to contact emergency services directly for life-threatening situations.

## Disclaimer

CampusAid is a hackathon prototype built for demonstration purposes. It is **not** a certified medical or emergency response tool. In a real emergency, always contact professional emergency services directly.

---

*Built for PromptWars × WIE-IEEE.*
