# Beacon Storm

A 3D boating game set in a storm over the Maldivian atolls. Gather glowing lanterns and bank them at Rasdhoo lighthouse, run ferries between islands, keep off the reefs, keep the bilge pumped, and go fishing on calm days for the Maafushi Fish Market.

The whole game is one file, `index.html`. It uses Three.js 0.160, loaded from the unpkg CDN. Everything else (models, textures, sound, the radio voice) is generated in the browser, so there are no other files to upload.

## Put it on GitHub Pages

1. Create a new repository on GitHub, for example `beacon-storm`. It can be public or private; private Pages needs a paid plan.
2. Upload the files:
   - **In the browser:** click **Add file → Upload files**, drag in `index.html`, `README.md` and `.nojekyll`, then **Commit changes**.
   - **From a terminal:**
     ```bash
     git init
     git add index.html README.md .nojekyll
     git commit -m "Beacon Storm"
     git branch -M main
     git remote add origin https://github.com/<your-username>/beacon-storm.git
     git push -u origin main
     ```
3. Go to **Settings → Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose **main** and **/ (root)**, and click **Save**.
4. After a minute or two the game is live at:
   `https://<your-username>.github.io/beacon-storm/`

`.nojekyll` tells GitHub Pages to serve the files as they are, without running them through Jekyll.

## Run it on your own computer

Some browsers block modules opened straight from disk (`file://`), so serve the folder with any small web server:

```bash
# Python 3
python3 -m http.server 8000
# or Node.js
npx serve .
```

Then open http://localhost:8000.

An internet connection is needed the first time, to fetch Three.js from unpkg.

## Controls

| Action | Keyboard | Touch |
|---|---|---|
| Throttle / brake | W / ↑, S / ↓ | Drag up / down anywhere |
| Steer | A D / ← → | Drag left / right |
| Bilge pump | E | PUMP button |
| Fish (calm days): cast, strike, reel | F (hold to reel) | CAST / STRIKE / REEL button |
| Push the boat off a beach | Hold W or Space | Hold to push button |
| Moor at a pier | Slow down at the end of the pier | |
| Pause / mute / settings | P, M, gear button | Buttons, top right |

## Notes

- The spoken VHF radio uses the browser's built-in speech voices. If your browser has none, the messages still appear as on-screen text. You can switch the voice off in Settings.
- Your best score, skipper look, volume settings and mute choice are saved in the browser's local storage.
- To pin the Three.js version or host it yourself, edit the `importmap` near the top of `index.html`.
