🌙 Introverse

An introvert's haven in the digital realm: discover anime, chat with an AI, savor daily quotations, enjoy soothing lo-fi background music, and have a private notebook.

 Features
Anime: Top ranked, airing and popular anime (Jikan API)
- 🌸 Chatbot — Chat with Hana, a cute AI friend (Gemini API)
- ✨Quotes — Daily wisdom on various topics
Music: curated lo-fi & ambient YouTube stations (Music)
Private journaling where user logs data with Firebase Auth

 Tech Stack
- HTML, CSS, vanilla JavaScript
- [Firebase Authentication](https://firebase.google.com/docs/auth) (Email/Password)
Google Gemini API for the chatbot
Anime data provided by the [Jikan API](https://jikan.moe/)

 Setup

 1. Firebase
This project utilizes Firebase Auth for logging in and out of the app (for login/register use in login.html, journal.html and the nav bar auth state for all pages). The Firebase client config provided in this repo is not a secret, it's a client identifier, see [Firebase's docs](https://firebase.google.com/docs/projects/api-keys) for more.

If you wish to choose your own Firebase project:
2. At [Firebase Console](https://console.firebase.google.com/), create a project.
2. Enable Authentication → Email/Password
4. Change the firebaseConfig / _fbc object to your own project's config in each HTML file

Be sure that the security rules for your Firestore/Storage data are appropriately restricted — not left alone in the "public test-mode" rules.

 2. Gemini API Key (required)
The chatbot located in the file `chat.html` requires a Gemini API key:
2. Sign up for a FREE key at [Google AI Studio](https://aistudio.google.com/apikey)
3. View the chat.html file, and change YOUR_GEMINI_API_KEY_HERE to your key

⚠️ Note: Once you add this key it goes into the page source, so anyone who views that source will be able to see it in the client side JavaScript. In case of a public/production deployment, it's recommended to proxy to Gemini through a small backend/serverless function, to keep your key private and to add usage limits. If it is for personal/local use only then it is OK to add it directly.

 Running Locally
Simply navigate to index.html in a browser to get full YouTube embed support for the Music page; or use any static server (such as VS Code Live Server) to serve the folder.