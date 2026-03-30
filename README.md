# Home Monitor — Deployment Guide

## What's in this folder

| File | Purpose |
|------|---------|
| index.html | The full dashboard app |
| manifest.json | PWA config (enables "Add to Home Screen") |
| sw.js | Service worker (offline support) |

---

## How to host this (free options)

### Option A — Netlify (easiest, recommended)
1. Go to netlify.com and create a free account
2. Drag the entire `home-monitor` folder onto the Netlify dashboard
3. You'll get a URL like `https://your-home-monitor.netlify.app`
4. Share that URL with your wife — she can add it to her home screen too

### Option B — GitHub Pages (free, permanent)
1. Create a free GitHub account
2. Create a new repository named `home-monitor`
3. Upload all files in this folder
4. Go to Settings → Pages → Deploy from main branch
5. Your URL: `https://yourusername.github.io/home-monitor`

---

## Adding real ESP32 data

Once your hardware is set up, the ESP32 will POST data to a simple API endpoint.
The dashboard will be updated to fetch from that endpoint automatically.

### ESP32 POST format (JSON)
```json
{
  "temp_f": 72.4,
  "humidity": 48.2,
  "supply_temp_f": 57.8,
  "return_temp_f": 71.9,
  "leak_kitchen": false,
  "leak_basement": false,
  "leak_utility": false
}
```

### Free backend options
- **Supabase** (supabase.com) — Free PostgreSQL database with REST API
- **Firebase** (firebase.google.com) — Free real-time database from Google
- **ThingSpeak** (thingspeak.com) — Built specifically for IoT sensor data

We'll set one of these up together in a future session.

---

## Installing as a phone app

### iPhone
1. Open the dashboard URL in Safari
2. Tap the Share button (square with arrow)
3. Tap "Add to Home Screen"
4. Tap "Add" — it will appear on your home screen like a real app

### Android
1. Open the dashboard URL in Chrome
2. Tap the three-dot menu
3. Tap "Add to Home Screen" or "Install App"

---

## Alert thresholds
Thresholds are configurable directly in the app under the "Alert thresholds" section.
Future versions will support push notifications to your phone.
