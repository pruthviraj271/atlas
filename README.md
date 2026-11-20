# OpenChat Atlas

A free-first index of official AI chatbot destinations — 35 verified routes to ChatGPT, Claude, Gemini, and the wider chatbot field.

## 🚀 Quick Start

**No build step required.** Just open `index.html` in a browser, or serve it:

```bash
# Python 3
python -m http.server 8000

# Node.js (npx)
npx serve .

# PHP
php -S localhost:8000
```

Then visit `http://localhost:8000`

## 📁 Project Structure

```
atlas/
├── index.html      # Complete single-page app (HTML + CSS + JS)
├── data.json       # Structured data for all 35 entries
├── data.js         # ES module export of the data
└── README.md       # This file
```

## 🎯 Features

- **35 official chatbot destinations** — curated, verified, no wrappers
- **Free-first clarity** — access badges: Free to use / Free to start / Free to browse / Free plan / Not free by default
- **Instant client-side search** — filters name, category, description, tags, value (⌘/Ctrl+K to focus)
- **Light/Dark mode** — persists preference, respects system setting
- **Zero dependencies** — vanilla HTML/CSS/JS, ~15KB gzipped
- **Accessible** — semantic HTML, ARIA labels, keyboard navigation, reduced motion support
- **Responsive** — 1/2/3 column grid, mobile-first

## 📊 Data Schema

Each entry in `data.json`:

```json
{
  "id": 1,
  "category": "OpenAI",
  "room": "The main room",
  "name": "ChatGPT Free",
  "desc": "Ask, write, learn, plan, and explore...",
  "tags": ["Chat", "Search", "Voice"],
  "access": "free",
  "accessLabel": "Free to use",
  "value": "Best all-rounder",
  "url": "https://chat.openai.com"
}
```

**Access types:** `free` | `browse` | `plan` | `try` | `paid`

**Categories:** `OpenAI` | `Explore` | `Build` | `Everyday` | `Research` | `Companions` | `Characters` | `Open models`

## 🔧 Using the Data

### As ES Module (data.js)
```javascript
import { atlasData, accessTypes, categories } from './data.js';

console.log(atlasData.length); // 35
console.log(atlasData[0].name); // "ChatGPT Free"
```

### As JSON (fetch)
```javascript
const res = await fetch('./data.json');
const { entries, accessTypes, categories } = await res.json();
```

### Node.js / Bun
```javascript
import { readFileSync } from 'fs';
const { entries } = JSON.parse(readFileSync('./data.json', 'utf-8'));
```

## 🎨 Customization

### Colors (CSS Custom Properties)
Edit `:root` in `index.html`:
```css
:root {
  --accent: #e8e8e8;      /* Primary action color */
  --green: #22c55e;       /* Free badge */
  --blue: #3b82f6;        /* Browse badge */
  --amber: #f59e0b;       /* Plan badge */
  --red: #ef4444;         /* Paid badge */
  --purple: #a855f7;      /* Try badge */
}
```

### Fonts
Currently: **Space Grotesk** (display) + **IBM Plex Mono** (data)
Change in `<head>` Google Fonts link and `--font-display`/`--font-mono` variables.

## 📝 Adding/Updating Entries

1. Edit `data.json` — add a new object to `entries` array
2. Increment `meta.totalEntries` and `meta.updated`
3. Run a quick test by opening `index.html`

The site auto-renders from the data array — no HTML editing needed.

## 🌐 Deployment

### Static Hosting (Recommended)
- **Netlify**: Drag & drop the `atlas` folder
- **Vercel**: `vercel deploy atlas`
- **GitHub Pages**: Push to repo, enable Pages
- **Cloudflare Pages**: Connect repo, build command: `none`
- **Surge**: `surge atlas/`

No build configuration needed — it's pure static files.

## 📄 License

MIT — Free to use, modify, and distribute.

## ⚠️ Disclaimer

OpenChat Atlas is an independent index. Not affiliated with OpenAI, Anthropic, Google, Microsoft, Meta, xAI, or any listed provider. Always verify current features, pricing, and terms at the official destination.

---

**Built with** vanilla HTML/CSS/JS • **Fonts** via Google Fonts • **Icons** inline SVG