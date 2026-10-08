# Orbit Orchard

Original responsive HTML5 arcade game. Plain HTML, CSS, JavaScript; no build step, packages, backend, or external game assets. All five pages load the supplied Google AdSense script for advertising. Open `index.html` directly to play, or serve the folder:

```sh
cd /workspace/mmo
python3 -m http.server 8000 --bind 0.0.0.0
```

Deploy all `.html`, `.css`, `.js`, `.svg`, and `robots.txt` files together to a static HTTPS host. Relative links support subdirectory hosting. See `ADSENSE-LAUNCH.md` before applying for advertising.

## Files

- `index.html`: main menu, canvas game, leaderboard, original explanatory content
- `game.js`: animation, collisions, endless levels, synthesized optional audio, local storage
- `styles.css`: responsive layout and shared page styles
- `about.html`, `how-to-play.html`, `contact.html`, `privacy.html`: supporting pages
- `favicon.svg`, `robots.txt`: website assets and crawler guidance

## Gameplay

Catch stars for 100 points each; every ten stars adds a level. Avoid debris; three hits end a run. Brief protection follows each hit. Keyboard: arrows or A/D; P pauses. Mouse: move over the canvas. Touch: drag. Tab changes pause automatically. Restart discards the unfinished run. Top five completed scores and sound preference remain locally when browser storage is available. Clearing scores does not reset sound preference.

## Validation

Chromium browser checks exercise scoring, level progression, pause/resume, restart, sound preference, game over, score persistence and clearing, supporting page responses, and mobile overflow. No dependencies are required to run the website. Local storage can be blocked without preventing play.

## Advertising document structure

The game canvas and AdSense script are in the top-level HTML document. There are no site-authored iframes or embedded game documents. The script is present once in each page head; Auto ads manages placements in that page, with no manual ad units configured. Google may use its own internal iframes to render ad creatives. Configure Auto ads exclusions in AdSense for the `.game-layout` area and disable overlay formats if needed to keep ads away from gameplay controls. Advertising cannot be validated as serving until the site is deployed and approved.
