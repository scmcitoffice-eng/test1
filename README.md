# Inventory Management System

A static inventory app with Firebase Realtime Database, ready to deploy on Vercel.

## Project structure

```
inventory-app/
├── public/
│   └── index.html      ← the entire app
├── vercel.json         ← Vercel routing + security headers
└── README.md
```

## Deploy to Vercel

### Option A — Vercel CLI (fastest)

```bash
npm i -g vercel
cd inventory-app
vercel
```

Follow the prompts. Your app will be live at a `*.vercel.app` URL.

### Option B — Vercel Dashboard (drag & drop)

1. Go to https://vercel.com/new
2. Drag the entire `inventory-app` folder onto the import area.
3. Click **Deploy** — no build settings needed.

### Option C — GitHub (recommended for ongoing updates)

1. Push this folder to a GitHub repo.
2. Connect the repo in the Vercel dashboard.
3. Vercel auto-deploys on every push to `main`.

---

## Firebase setup

Make sure your Firebase Realtime Database rules allow reads/writes.
For development, in the Firebase Console set:

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

For production, restrict access with authentication rules:

```json
{
  "rules": {
    ".read":  "auth != null",
    ".write": "auth != null"
  }
}
```

Also add your Vercel domain to the **Authorized domains** list in:
Firebase Console → Authentication → Settings → Authorized domains

---

## Updating Firebase credentials

The Firebase config is stored in `<meta>` tags at the top of `public/index.html`.
To update, just edit those tag `content` values directly.
