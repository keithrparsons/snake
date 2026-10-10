# Pocket Snake Color

A snake game in one HTML file, styled as a Game Boy Color in WLAN Pros colors.

- **Live:** https://snake.wlanpros.com (also https://wlanpros-snake.netlify.app)
- **Netlify site:** `wlanpros-snake`, team `wlanpros`, site id `f8aad1ee-7e83-41d7-95f5-cf43fc07ad5e`
- **DNS:** `snake` CNAME to `wlanpros-snake.netlify.app`, added by Matthew Casteel on 2026-10-10. HTTPS is Netlify's Let's Encrypt certificate.

## Files

- `index.html`: the whole game (HTML, CSS and JavaScript; music is generated live with Web Audio, no audio files)
- `wlanpros-logo-white.svg`: copied from `myPKA/Team Knowledge/Brand-Assets/WLANPros-Logo_2026/WLAN Pros Logo White/`

## Run locally

```bash
python3 -m http.server 8777 --bind 127.0.0.1 --directory ~/snake-code
```

Then open http://localhost:8777. In myPKA's Claude Desktop session this is the `snake` entry in `.claude/launch.json`.

## Deploy

```bash
cd ~/snake-code && netlify deploy --prod --dir . --site f8aad1ee-7e83-41d7-95f5-cf43fc07ad5e
```

## What's in it (as of 2026-10-10)

- Keyboard (arrows, WASD), mouse steering toward the pointer, clickable D-pad; the snake can't reverse into itself
- Speed 1 to 10, board sizes 12/16/20/28, score and a remembered high score (per browser, `localStorage`)
- Shell colors: WLAN Pros (default), Lime, Slate, White, Grape, Atomic Purple
- Seven chiptune tracks (two public-domain melodies: Korobeiniki and Grieg's Hall of the Mountain King; five originals), music on/off, master volume
- Apple beep (off by default) and game-over sound, both soft sine tones, with their own effects volume
- Path hint: a faint dashed line on the shortest safe route to the apple
- Autopilot after 1 to 5 seconds with no input, any control takes back over; a toggle decides whether autopilot games count toward the high score
- Buttons: A or START start/pause, B music, SELECT mouse steering
