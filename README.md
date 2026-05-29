# 🌸 A Little Movie-Date Invitation

A soft, no-pressure Valentine-style invitation web page — a single self-contained `index.html`
that walks someone gently through a movie-date plan and lets them pick the movie(s), day, and showtime.

> Built to be **kind first**: the very first screen makes it clear there's zero pressure, and the
> "Maybe another time" button is playful, never pushy.

---

## ✨ What it does

1. **Gentle intro** — a warm, no-pressure note with a polaroid photo.
2. **The plan** — pick-up → lunch at Din Tai Fung (SM North) → short walk to Trinoma → movie(s) →
   optional dessert/coffee → a safe ride home.
3. **Pick the movie(s)** — *Obsession (2026)* and/or *Colony (2026)*. Choose one, or both for a double feature.
4. **Pick the day** — Sat May 30 or Sun May 31.
5. **Pick a showtime** — real Trinoma showtimes. For a double feature, times that overlap the other
   film are automatically crossed out so the plan is always feasible.
6. **Summary** — auto-computes the whole day's timeline (pick-up time, lunch, movie, dessert, home),
   with **Text me / Call me** buttons and a prompt to screenshot & send the choice back.

### Cute touches
- 🌹 Rose petals drift across the screen and burst on every transition.
- 😹 The "Maybe another time" button **dodges** the cursor and teases; after ~10 tries it gives up,
  the cat memes swarm the screen, and a gentle "no pressure for real" plea appears.

---

## 🚀 How to use it

### View it locally
No build step, no dependencies. Either:

- **Just open it** — double-click `index.html`, **or**
- **Serve it** (recommended, so images load reliably):
  ```bash
  python3 -m http.server 8088
  ```
  then open <http://localhost:8088/>.

### Publish it for free on GitHub Pages
1. Push this folder to a GitHub repo (already done if you're reading this on GitHub).
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source: Deploy from a branch**, **Branch: `main` / `root`**.
4. Save. After a minute your link will be live at:
   `https://<your-username>.github.io/movie-invitation/`
5. Share that link. It works on **iPhone, Android, and desktop**.

---

## 🛠️ Customizing

Everything lives in `index.html`. Common tweaks:

| Want to change… | Where |
|---|---|
| Phone number (Text/Call buttons) | `var MY_NUMBER = "+639682819821";` near the top of the `<script>` |
| Showtimes | the `SHOWTIMES = { ... }` object |
| Movie runtimes (for double-feature math) | the `RUNTIME = { ... }` object |
| Timing (travel / wait / eat / walk / dessert) | `TRAVEL`, `WAIT`, `EAT`, `WALK`, `DESSERT` constants |
| Intro message / wording | the `#s0` section near the top of `<body>` |
| Photo crop in the polaroid | `.polaroid img { object-position: center 38% }` (lower % shows more of the top) |

### Replacing the images
Keep the **same filenames** and the page picks them up automatically:

| File | Used for |
|---|---|
| `nicky.jpg` | the polaroid photo on the intro screen |
| `obsession.png` | Obsession movie poster |
| `colony.png` | Colony movie poster |
| `cat1.png`, `cat2.png`, `cat3.png` | the crying-cat swarm + the plea popup |

If any image is missing, the page falls back gracefully (gradient placeholders / emoji cats).

---

## 📁 Contents

```
movie-invitation/
├── index.html      ← the entire app (HTML + CSS + JS inline)
├── nicky.jpg
├── obsession.png
├── colony.png
├── cat1.png
├── cat2.png
├── cat3.png
└── README.md
```

No frameworks, no build, no tracking. Just one HTML file and six images. 💗
