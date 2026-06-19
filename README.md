# MatchMind AI — Football Intelligence Platform

> Elite-level AI tactical analysis for professional football clubs, coaches, and analysts.

---

## 🚀 Quick Start

### Prerequisites
- **Node.js** v18+ ([download](https://nodejs.org))
- **npm** v9+
- A **Gemini API key** (optional — demo mode works without one)

---

### 1. Install Dependencies

```bash
# From the root matchmind-ai folder:
npm run install:all
```

This installs packages for root, client, and server.

---

### 2. Configure Environment

```bash
cd server
cp .env.example .env
```

Open `server/.env` and add your Gemini key:

```
GEMINI_API_KEY=your-gemini-key-here
PORT=3001
NODE_ENV=development
```

> ⚠️ Without a key, the platform runs in **demo mode** — it generates realistic AI-style reports automatically. The full platform works immediately with seed data.

---

### 3. Start the Application

```bash
# From the root matchmind-ai folder:
npm run dev
```

This starts both servers concurrently.

---

## 🌐 Access URLs

| Service | URL |
|---|---|
| **Frontend (React)** | http://localhost:3000 |
| **Backend API** | http://localhost:3001 |
| **API Health Check** | http://localhost:3001/api/health |

**Open your browser at: http://localhost:3000**

---

## 🔑 Demo Login Credentials

| Role | Email | Password |
|---|---|---|
| Head Coach | coach@matchmind.ai | demo1234 |
| Lead Analyst | analyst@matchmind.ai | demo1234 |

Or use **Sign in with Google** (demo mode — no real OAuth required).

---

## 📱 Platform Features

### Pages
- **Dashboard** — KPIs, trend charts, recent reports, AI coaching insights
- **Upload Match** — Drag & drop .mp4 upload with real-time processing progress
- **Match Reports** — All analysed matches with search and filtering
- **Report Detail** — 6-tab deep-dive: Overview, Tactics, Pressing, Players, Opposition, Coaching
- **Team Analysis** — Radar charts, form index, season aggregates
- **Player Analysis** — Per-player ratings, key actions, strengths/weaknesses
- **Opposition Scouting** — Exploitable areas, weaknesses, press profiles

### AI Analysis Sections
Each report includes:
- Match Summary (3-paragraph executive brief)
- Score & Possession
- Formation Analysis with visual diagrams
- Tactical Strengths & Weaknesses
- Pressing Structure & Triggers
- Defensive Line Analysis
- Attacking Pattern Breakdown
- Transition Analysis
- Player Performance Ratings
- Opposition Tendencies
- Momentum Chart
- Coaching Recommendations (prioritised)

---

## 🏗️ Architecture

```
matchmind-ai/
├── client/               # React frontend (port 3000)
│   └── src/
│       ├── pages/        # All page components
│       ├── components/   # Layout, sidebar, topbar
│       ├── hooks/        # Auth context
│       └── utils/        # API calls
├── server/               # Express backend (port 3001)
│   ├── routes/
│   │   ├── analyze.js    # Video upload + Gemini AI analysis
│   │   └── reports.js    # Seed demonstration data
│   └── uploads/          # Temporary video storage (auto-cleaned)
└── package.json          # Root with concurrently scripts
```

---

## 🔧 Scripts

| Command | Description |
|---|---|
| `npm run install:all` | Install all dependencies |
| `npm run dev` | Start both frontend + backend (development) |
| `npm run build` | Build React frontend for production |

---

## 🔒 Security Notes

- Gemini key is stored server-side only — never exposed to the client
- Uploaded videos are deleted from disk after analysis
- Rate limiting: 50 requests per 15 minutes per IP
- CORS restricted to localhost:3000

---

## 📦 Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 18, React Router 6, Recharts |
| Styling | Custom CSS with design tokens (dark theme) |
| Backend | Node.js, Express |
| AI | Google Gemini 1.5 Pro |
| Upload | Multer (500MB limit) |
| Auth | Local state (extend with Supabase Auth) |

---

## 🔌 Extending with Supabase

To add persistent storage, replace the in-memory `analysisStore` Map in `server/routes/analyze.js` with Supabase queries:

```bash
npm install @supabase/supabase-js
```

Add to `server/.env`:
```
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_KEY=your-anon-key
```

---

Built for elite football clubs. Turns footage into intelligence. ⚽
