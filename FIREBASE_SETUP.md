# Firebase + Telegram Mini App setup

The repository contains the Arena Duel static app. Firebase Web configuration is intentionally not filled in because each Firebase project has unique values.

## 1. Create Firebase project

1. Open https://console.firebase.google.com/
2. Create a project.
3. Open **Project settings** → **Your apps** → add a **Web app**.
4. Copy the web configuration into `firebase-config.example.js` and save the file as `firebase-config.js`.
5. Add these scripts before the application script in `index.html`:

```html
<script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-firestore-compat.js"></script>
<script src="firebase-config.js"></script>
```

6. Initialize Firebase once in the app:

```html
<script>
  firebase.initializeApp(window.ARENA_FIREBASE_CONFIG);
  const db = firebase.firestore();
</script>
```

## 2. Firestore

Create a Firestore database in production mode, then publish the checked-in `firestore.rules` file from the Firebase console. Do not store teacher PINs in a public Firestore collection. For teacher login use Firebase Authentication or a trusted backend.

A browser-only Firebase config is not a secret. Never put a service-account JSON file or private API key into `index.html`.

## 3. Telegram Mini App

The app can be hosted at:

`https://sosovs46-ops.github.io/arena-duel/`

Use that HTTPS URL in BotFather as the Web App URL. The Telegram Web App SDK is already available in the newer source file you supplied, but Telegram `sendData` only works when the page is opened inside Telegram and a bot callback is configured.

## Current limitation

The repository's current `index.html` is the earlier standalone build. Firebase cannot be fully activated until a real Firebase web configuration is supplied and the newer source is made the repository's `index.html`. This template and security baseline are committed so the remaining setup is explicit and safe.
