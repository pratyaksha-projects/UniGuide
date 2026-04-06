# UniGuide — HBTU Kanpur Campus Navigator

> An interactive, Google Maps–style campus navigation web app for HBTU Kanpur.
> Helps new students, visitors, and staff find any department, office, or facility — with walking directions, fuzzy search, and live GPS support, to navigate them in real time.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-blue?style=flat-square)](https://YOUR_USERNAME.github.io/uniguide)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)
[![Made for HBTU](https://img.shields.io/badge/Campus-HBTU%20Kanpur-orange?style=flat-square)]()

---

## What it does

- **Real map** — renders HBTU Kanpur on OpenStreetMap via Leaflet.js
- **Smart fuzzy search** — finds places even with typos (`laibrery` → Library, `meckhanical` → Mechanical)
- **Alias search** — Hindi & common shortforms work (`khana` → Canteen, `deo office` → Admin)
- **GPS directions** — tap "My location" and get a walking route to any building
- **Embeddable** — drop one `<iframe>` tag on any college website
- **Zero cost** — no API keys, no server, no database. Runs 100% in the browser, so it may work without burden on pocket.

---

## Live Demo

[https://github.com/pratyaksha-projects/UniGuide] in this link.

---

## Tech Stack

| Layer | Tool | Cost |
|-------|------|------|
| Map rendering | [Leaflet.js](https://leafletjs.com) v1.9.4 | Free |
| Map tiles | [OpenStreetMap](https://openstreetmap.org) | Free |
| Routing | Browser geometry (straight-line on campus) | Free |
| Search | Custom fuzzy JS engine | Free |
| Hosting | GitHub Pages | Free |
| Data | `index.html` inline JSON | Free |

---

## Project Structure

```
uniguide/
├── index.html        ← entire app (map + search + routing + UI)
├── README.md         ← this file
├── LICENSE           ← MIT license
├── CONTRIBUTING.md   ← how others can add places
└── docs/
    ├── ADDING_PLACES.md     ← guide to add new buildings
    ├── EMBED_GUIDE.md       ← how to embed on college website
    └── screenshots/
        └── preview.png
```

---

## How to Add or Update a Campus Location

Open `index.html` and find the `PLACES` array. Add a new entry like this:

```js
{
  id: 'unique-id',
  name: 'Full Building Name',
  cat: 'Department',        // Department | Admin | Facility | Hostel | Food | Landmark
  lat: 26.47250,            // GPS latitude  (get from Google Maps -> right click -> copy)
  lng: 80.27700,            // GPS longitude
  info: 'Short description shown in the info card.',
  floor: 'Ground – 2nd Floor',
  aliases: ['short name', 'hindi name', 'common typo']
}
```
---

## Embedding on Another Website

```html
<iframe
  src="https://github.com/pratyaksha-projects/UniGuide" # later i will do it ...
  width="100%"
  height="600px"
  style="border:none; border-radius:12px;"
  title="HBTU Campus Map"
  loading="lazy"
  allow="geolocation">
</iframe>
```

---

## Setup & Deployment

### 1. Fork or clone this repo
```bash
git clone https://github.com/pratyaksha-projects/UniGuide
cd uniguide
```

### 2. Open locally
Just open `index.html` in any browser. No server needed.

### 3. Deploy to GitHub Pages
- Go to your repo -> **Settings** -> **Pages**
- Source: `main` branch, `/ (root)` folder
- Save -> live URL appears in ~60 seconds

---

## GPS Accuracy Note

Campus GPS on phone works within 5–15 metres. The walking routes shown are straight-line estimates — actual walking paths follow campus roads. Future versions may include a hand-drawn path graph for turn-by-turn directions.

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Anyone can submit a PR to add missing buildings, fix GPS coordinates, or add aliases.

---

## License

MIT — free to use, modify, and share. See [LICENSE](LICENSE).

---

## Author

Built by [Pratyaksha Saini](https://github.com/pratyaksha-projects/UniGuide) · Student, HBTU Kanpur  
If this helped you, give it a ⭐ — it helps others find it.
