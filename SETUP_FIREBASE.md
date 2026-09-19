# Firebase setup for Arena: Duel

1. Go to Firebase Console: https://console.firebase.google.com/
2. Create a new Firebase project or open an existing one.
3. In Project settings -> Your apps -> Web app, copy the Firebase config values.
4. Open `firebase-config.js` in the project root and replace the placeholders with your real values.
5. Add this script tag to `index.html` before the game script:

```html
<script src="https://telegram.org/js/telegram-web-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-firestore-compat.js"></script>
<script src="./firebase-config.js"></script>
```

6. In Firebase Console, enable Firestore Database.
7. If Firebase is not configured yet, the app still works in local mode and saves results to `localStorage`.

Important:
- Do not share real API keys in public repos.
- For Telegram Mini App, deploy the site over HTTPS (GitHub Pages or another hosting).
