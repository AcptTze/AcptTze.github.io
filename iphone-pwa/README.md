# Password Manager – iPhone (PWA)

Same idea as the desktop app: unlock with master password, add entries, copy passwords. Works **offline** on your iPhone after you add it to the home screen.

## How to use on iPhone

1. **Put the app on the web** (required for “Add to Home Screen” and HTTPS):
   - Upload the whole `iphone-pwa` folder to any web host, for example:
     - **GitHub Pages**: create a repo, upload these files, enable Pages in repo Settings.
     - **Netlify** / **Vercel**: drag-and-drop the folder to deploy.
     - Your own server: copy the folder into your web root.
   - You need a URL like `https://yoursite.com/` (or `https://yoursite.com/iphone-pwa/` if you put the folder in a subpath). **HTTP is not enough** for the app to install properly on iPhone.

2. **On your iPhone**:
   - Open **Safari** and go to that URL (e.g. `https://yoursite.com/`).
   - Tap the **Share** button (square with arrow).
   - Tap **Add to Home Screen**.
   - Name it (e.g. “Passwords”) and tap **Add**.

3. **Use it**:
   - Open the new icon like any app. Unlock with your master password, add entries, tap “Copy password” to copy. Tap “Lock” when done. It works offline after the first load.

## Running locally (no server)

- You can open `index.html` in a browser on your PC to test.
- On iPhone, “Add to Home Screen” and offline/install behavior require the app to be served over **HTTPS** from a real URL, so you need step 1 (upload to a host) for the full app experience on the phone.

## Data

- Vault is encrypted (same style as desktop: PBKDF2 + AES-GCM) and stored in the browser on the device.
- This PWA uses its **own** vault (separate from the Windows exe). Entries don’t sync between the two unless you add export/import later.
