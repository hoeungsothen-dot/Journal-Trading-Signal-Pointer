# Trading Journal — Web App

A professional ICT trading journal with calendar views, statistics, and monthly report export. Built as a fully offline-capable PWA.

## Features

- **Week / Month / Year** calendar views
- **Trade logging** — symbol, direction, entry/SL/TP/exit, lot, outcome, ICT setup, session, emotions, notes
- **Live R:R calculator** in trade form
- **Monthly summary panel** — win rate, avg RR, RR distribution, advance badge
- **Monthly Report Export**:
  - 📊 **CSV** — Full trade list + summary block; UTF-8 BOM for Excel/Google Sheets
  - 📄 **PDF** — Rich formatted report; opens in new tab → Print → Save as PDF
- **Dark / Light theme** toggle
- **PWA** — installable on desktop & mobile, works offline
- All data stored in `localStorage` — 100% private, no server

---

## Project Structure

```
trading-journal/
├── index.html      ← Main app (single file)
├── manifest.json   ← PWA manifest
├── sw.js           ← Service worker (offline support)
├── icon.svg        ← App icon
└── README.md
```

---

## Deploy to GitHub Pages + Cloudflare

### 1 — Push to GitHub

```bash
git init
git add .
git commit -m "Initial: Trading Journal web app"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/trading-journal.git
git push -u origin main
```

### 2 — Deploy with Cloudflare Pages

1. Go to [dash.cloudflare.com](https://dash.cloudflare.com) → **Workers & Pages** → **Create application** → **Pages**
2. **Connect to Git** → select your `trading-journal` repository
3. Build settings:
   - **Framework preset**: None
   - **Build command**: *(leave empty)*
   - **Build output directory**: `/` (root)
4. Click **Save and Deploy**

Cloudflare will give you a `*.pages.dev` URL immediately. You can also add a custom domain in the Pages dashboard.

### 3 — Optional: GitHub Pages fallback

Go to repo **Settings → Pages → Source: main branch / root** → Save.  
Your app will be live at `https://YOUR_USERNAME.github.io/trading-journal/`

---

## PDF Export Notes

The PDF export opens a styled HTML report in a new browser tab and auto-triggers the print dialog. In the print dialog:

- **Destination**: Save as PDF
- **Paper size**: A3 Landscape (recommended for full table)
- **Margins**: Minimum / None
- **Background graphics**: ✅ Enable (for dark theme colors)

---

## Data & Privacy

All trade data is stored in your browser's `localStorage`. No data is ever sent to any server. Clearing browser data will erase your trades — export CSV regularly as backup.

---

## License

MIT — use freely for personal trading.
