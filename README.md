# Akhu & Munu: Study Tracker

A shared daily-targets tracker. Static site (GitHub Pages) + Firebase (free) for sign-in and live-synced storage. No server, no storage bucket, no cost at this scale.

## One-time Firebase setup (about 10 minutes)
1. Go to https://console.firebase.google.com and click **Add project**. Turn Google Analytics off.
2. **Build > Firestore Database > Create database.** Choose a location near you (for example asia-south1 or asia-south2) and **Production mode**.
3. **Build > Authentication > Get started > Sign-in method > Google > Enable.** Pick a support email and save.
4. **Project settings (gear icon) > Your apps > Web (</>)**. Register the app (no hosting). Copy `apiKey`, `authDomain`, `projectId`, `appId` into `config.js`, and set both emails in `config.js`.
5. **Firestore > Rules.** Paste the contents of `firestore.rules` (with both emails changed) and click **Publish**.

## Publish on GitHub Pages
1. Create a new repository on GitHub. A free account needs it to be **public** for Pages. Your data stays private because only the two emails pass the Firestore rules; the Firebase keys in `config.js` are not secrets.
2. Upload `index.html`, `config.js`, `firestore.rules`, `README.md`.
3. **Settings > Pages > Build and deployment:** Source = **Deploy from a branch**, Branch = **main**, folder **/(root)**, Save.
4. Wait a minute. Your URL is `https://YOUR-USERNAME.github.io/REPO-NAME/`.
5. **Firebase > Authentication > Settings > Authorized domains > Add domain:** `YOUR-USERNAME.github.io`.

## Share
Send Munu the URL. She taps **Sign in with Google** using the email set in `config.js`. That's it.

## Features
Daily targets with 0-100% completion, goals with due dates, notes, history with chart, streaks, time studied, carry over unfinished targets, CSV export, live sync, and offline support (changes sync when you're back online).
