# Verse Hunt

A real-time multiplayer Bible verse deduction game (Hider vs Hunters, Action Points).
Static site: GitHub Pages hosts it, a free Firebase Realtime Database syncs the rooms.

## Setup (about 10 minutes, no coding)

### 1. Create the Firebase database
1. Go to https://console.firebase.google.com and sign in with a Google account.
2. **Add project**, name it (for example `verse-hunt`). Turn Google Analytics off.
3. In the left menu choose **Build > Realtime Database > Create Database**. Pick a location and choose **Start in locked mode**.
4. Open the **Rules** tab, replace everything with the contents of `database.rules.json`, then **Publish**.

### 2. Register a web app
1. Project settings (gear icon) > **General** > under *Your apps* tap the **</>** (Web) icon.
2. Give it any nickname. Skip Firebase Hosting.
3. Copy the `firebaseConfig` values it shows you.

### 3. Add the config
Open `firebase-config.js` in this repo and replace each `YOUR_...` value with yours. Make sure `databaseURL` is included. If the console does not show it, copy the URL from the Realtime Database page (it starts with `https://` and ends with `firebaseio.com`).

### 4. Publish on GitHub Pages
1. Create a new GitHub repository and upload all files in this folder (**Add file > Upload files** works from a browser or phone).
2. Repo **Settings > Pages**. Under *Build and deployment* choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then Save.
3. After a minute your game is live at `https://YOUR-USERNAME.github.io/YOUR-REPO/`.

### 5. Play
1. One person opens the link, taps **Host a room**, and chooses Hider or Hunter.
2. Everyone else opens the same link and enters the 4-letter code, or scans the QR code in the **Room** pop-up.
3. The Hider enters a book, chapter and verse, taps **Fetch verse text**, checks it, and locks it in. The host taps **Start round**.

The badge at the top reads **Sync: live** when Firebase is connected, and **Sync: this browser only** when it is not configured.

## Credits and rights
Code created by CrossCode Ministry. © 2026 CrossCode Ministry. All rights reserved. Contact: crosscodeministry@gmail.com

## Notes
- Fetched verse text is the public-domain KJV (from bible-api.com). The NKJV is copyrighted, so it is not bundled. The host can paste licensed NKJV lines (`Book|Chapter|Verse|text`) in the lobby, or the Hider can type or paste NKJV text before locking in.
- The rules above leave rooms open to anyone who has your site, which suits a game among friends. The secret verse is stored in the room data, so a technical player could look it up. Delete old rooms from the Firebase console now and then.
- Cooldowns and timers use each device's clock.
