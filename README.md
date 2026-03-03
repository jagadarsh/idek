# cool movies

Dark gold streaming site — pstream-inspired design, Cloudflare Pages ready.

## File Structure

```
/
├── index.html          ← markup
├── css/
│   └── style.css       ← all styles
├── js/
│   ├── config.js       ← API key + password + embed settings
│   └── app.js          ← all logic
├── _headers            ← Cloudflare security headers
└── _redirects          ← Cloudflare SPA routing
```

---

## Setup (5 minutes)

### 1. Get a free TMDB API key
1. Create an account at https://www.themoviedb.org/
2. Go to **Settings → API → Create → Developer**
3. Copy your **API Key (v3 auth)** — looks like `a1b2c3d4e5f6...`

### 2. Paste it in config.js
Open `js/config.js` and replace:
```js
TMDB_KEY: 'YOUR_TMDB_API_KEY_HERE',
```

### 3. Deploy to Cloudflare Pages
1. Push this entire folder to a **GitHub repo**
2. Go to https://pages.cloudflare.com → **Create application → Pages → Connect to Git**
3. Select your repo
4. Framework preset: **None**
5. Build command: *(leave blank)*
6. Build output: *(leave blank or `/`)*
7. **Save and Deploy** ✓

---

## Customisation

| What                  | Where                              |
|-----------------------|------------------------------------|
| Password              | `js/config.js` → `PASSWORD`        |
| Gold accent colour    | `css/style.css` → `--gold`         |
| Add/remove row genres | `js/app.js` → `loadHome()`         |
| Embed provider        | `js/config.js` → `EMBED_BASE`      |

---

## Embed URL Format (Vidking)

| Type  | URL pattern |
|-------|-------------|
| Movie | `https://www.vidking.net/embed/movie/{tmdb_id}` |
| TV    | `https://www.vidking.net/embed/tv/{tmdb_id}/{season}/{episode}` |

---

## Features

- 🔐 Password gate 
- 🎬 Hero banner — 7 trending, auto-rotates every 7.5 s with dot nav
- ⏯️ Continue Watching row with gold progress bars (localStorage)
- 📺 Rows: Trending, Top Rated, Action, Comedy, Horror, Sci-Fi, Popular Series
- 🎭 Genre browser (16 genres)
- 🎞️ Movies page with genre filter pills + infinite load more
- 📺 Series page with load more
- 🔍 TMDB multi-search
- 📋 Detail modal:
  - Full backdrop image
  - Title, year, runtime, star rating, IMDb link
  - Overview / description
  - Genre tags
  - Director / Creator / Status / Budget info grid
  - Season picker + episode list with thumbnails, runtimes, progress bars
  - Cast row with photos + IMDb search links
  - "More Like This" recommendations row
- 🎬 Vidking.net embed player
- ✨ Grain texture, gold glow on hover, cinematic card zoom, scroll snap, fade-in on scroll, gold scrollbar
