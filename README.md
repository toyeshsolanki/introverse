# 🌙 Introverse

A quiet corner of the internet crafted for introverts — anime discovery, an AI companion, daily quotes, lo-fi music, and a private journal, all in one place.

## Features
- 🎌 **Anime** — Browse top-ranked, airing, and popular anime (Jikan API)
- 🌸 **Chatbot** — Talk to Hana, a cozy AI companion (Gemini API)
- ✨ **Quotes** — Daily wisdom across multiple categories
- 🎧 **Music** — Curated lo-fi & ambient YouTube stations
- 📓 **Journal** — Private journaling with Firebase Auth

## Tech Stack
- HTML, CSS, vanilla JavaScript
- [Firebase Authentication](https://firebase.google.com/docs/auth) (Email/Password)
- [Google Gemini API](https://ai.google.dev/) for the chatbot
- [Jikan API](https://jikan.moe/) for anime data

## Setup

### 1. Firebase
This project uses Firebase Auth for login/register (used in `login.html`, `journal.html`, and the nav bar auth state on every page). The Firebase client config included in this repo is safe to expose publicly (it's a client identifier, not a secret) — see [Firebase's docs](https://firebase.google.com/docs/projects/api-keys) for more.

If you want to use your **own** Firebase project instead:
1. Create a project at [Firebase Console](https://console.firebase.google.com/)
2. Enable **Authentication → Email/Password**
3. Replace the `firebaseConfig` / `_fbc` object in each HTML file with your own project's config

⚠️ Make sure your **Firestore/Storage security rules** are properly restricted (not left as public test-mode rules).

### 2. Gemini API Key (required)
The chatbot in `chat.html` needs a Gemini API key:
1. Get a free key at [Google AI Studio](https://aistudio.google.com/apikey)
2. Open `chat.html` and replace `YOUR_GEMINI_API_KEY_HERE` with your key

⚠️ **Note:** This key is used directly in client-side JavaScript, which means anyone viewing the page source can see it once you add it. For a public/production deployment, it's recommended to proxy Gemini requests through a small backend/serverless function so your key stays private and you can add usage limits. For personal/local use, adding it directly is fine.

## Running Locally
Just open `index.html` in a browser, or serve the folder with any static server (e.g. VS Code Live Server) for full YouTube embed support on the Music page.

## Pages
| File | Description |
|---|---|
| `index.html` | Home page |
| `anime.html` | Anime browser |
| `chat.html` | AI chatbot |
| `quotes.html` | Daily quotes |
| `music.html` | Lo-fi music player |
| `journal.html` | Private journal (requires login) |
| `login.html` | Login / Register |
