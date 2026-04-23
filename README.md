# Fresh Cuts Barbershop — AI Chatbot 💈

A single-file AI-powered chatbot for a fictional barbershop, built with vanilla HTML, CSS, and JavaScript. Powered by the **Google Gemini API** (free tier — no credit card needed).

🔗 **Live Demo:** https://nabeelnavas.github.io/barber-chatbot/

---

## Features

- 💬 Conversational AI assistant with full barbershop context
- 💈 Answers questions about prices, hours, location, and bookings
- 📅 Quick-reply suggestion buttons for common questions
- ⌨️ Typing indicator while the AI is responding
- 🔑 API key stored locally in the browser (never sent to any third party)
- 📱 Responsive design — works on mobile and desktop

---

## Tech Stack

| Part | Technology |
|------|------------|
| Frontend | HTML, CSS, Vanilla JavaScript |
| AI Model | Google Gemini 2.5 Flash (free tier) |
| API | Google Generative Language API |
| Hosting | GitHub Pages |
| Backend | None — fully client-side |

---

## How It Works

The chatbot sends the user's message along with the full conversation history to the Gemini API on every request. A system prompt containing the barbershop's details (prices, hours, barbers, location) is injected into every request so the AI always stays on topic and responds as a barbershop assistant.

```
User types message
       ↓
Browser sends POST request to Gemini API
       ↓
Gemini responds with barbershop-aware reply
       ↓
Reply is displayed in the chat UI
```

---

## Project Structure

```
barber-chatbot/
├── index.html    ← the entire app (HTML + CSS + JS in one file)
└── README.md
```

---

## Getting Started (Run Locally)

### 1. Clone the repo

```bash
git clone https://github.com/nabeelnavas/barber-chatbot.git
cd barber-chatbot
```

### 2. Get a free Gemini API key

1. Go to **https://aistudio.google.com/apikey**
2. Sign in with a Google account
3. Click **"Create API key"**
4. Copy the key — it starts with `AIza...`

> No credit card required. The free tier allows up to 1,000 requests/day.

### 3. Serve locally

You cannot open `index.html` by double-clicking — browsers block API calls from `file://` URLs (CORS policy). Use a local server instead:

```bash
# Python 3
python -m http.server 8000
```

Then open **http://localhost:8000** in your browser.

### 4. Use the chatbot

Paste your Gemini API key into the input at the top, click **Save**, and start chatting.

---

## Deployment

The app is hosted on **GitHub Pages** — no server or backend required since everything runs in the browser.

To deploy your own version:
1. Fork this repo
2. Go to **Settings → Pages**
3. Set source to `main` or `master` branch
4. Your site will be live at `https://YOUR-USERNAME.github.io/barber-chatbot/`

---

## Barbershop Details (Configured in System Prompt)

| | |
|---|---|
| **Location** | 22 Market Street, 5 min from city centre |
| **Hours** | Mon–Fri 9am–7pm, Sat 9am–6pm, closed Sunday |
| **Barbers** | Jake, Leo, and Sam |
| **Booking** | Call 07700 900 123 or freshcuts.co.uk |

| Service | Price | Duration |
|---------|-------|----------|
| Haircut | £12 | 30 mins |
| Skin Fade | £15 | 35 mins |
| Beard Trim | £8 | 15 mins |
| Haircut + Beard | £18 | 45 mins |
| Kids Cut (under 12) | £10 | 20 mins |
| Hot Towel Shave | £15 | 30 mins |

---

## Security Notes

- The API key is entered by the user at runtime and stored in `localStorage` — it is **never hardcoded** or committed to the repository
- All API calls go directly from the user's browser to Google's servers
- No user data is stored anywhere

---

## License

MIT — free to use and modify.
