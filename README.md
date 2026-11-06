# Lucky-Fortune-Wall
> An outdoor interactive installation prototype for Pride Square, Newtown — helping new residents discover local stories, places and events through a tarot-inspired card reading.
 
---
 
## Overview
 
Lucky Fortune Wall is a public-screen installation concept sited on Pride Square in the heart of Newtown, Sydney. A passerby approaches, draws three cards — **Past · Present · Future** — and each reading surfaces one local story, one Newtown place, and one small action to take next week.
 
Two or three people can read together. The installation analyses their combined readings and suggests a shared adventure they can do that week.
 
The prototype runs as a single HTML page, using MediaPipe for in-air hand gestures and a 3D CSS Fate Ring. It has a landscape desktop layout and an automatic portrait kiosk layout for vertical public-screen displays.
 
---
 
## Features
 
### Solo mode
- 6 interests to choose from: **Music · Art · Food · History · Hidden Places · Stories & Voices**
- Hidden Places splits into a *Quiet Corners* path and a *Mystical Newtown* path
- **3D Fate Ring** with 15 tarot cards — rotate with an open-palm circling gesture or a mouse drag
- Draw a card with a **closed fist** (held briefly) or a tap on the front card
- Each reading shows the card art, a short interpretation, a verified Newtown place, and a local event flyer
- **Peace sign** captures a souvenir postcard (3-2-1 countdown, decorative frame, downloadable)
### Together mode (2 or 3 players)
- **People picker** at the start locks the session count (Just me / Together → 2 or 3)
- Each player chooses their own interest and draws their own three cards
- **Handover screens** between players — "Pass the Fortune Wall to the next person"
- **Constellation page** compares all readings in a 3-column *Past / Present / Future* layout
- **Our Newtown Connection** — rule-based analysis classifies the group as one of:
  - **Shared Interest** — same theme across players
  - **Unexpected Harmony** — complementary themes from a predefined pair table (e.g. Music + History)
  - **Different Paths** — no strong match, framed positively
- Tarot-inspired interpretation templates fill in the players' actual card names and themes
- **Choose Our Next Stop** stage lets the group pick one adventure together
- Group souvenir postcard with the chosen adventure's fortune line
### Gestures
- Powered by **MediaPipe HandLandmarker** (loaded from CDN at runtime)
- Three recognised gestures:
  - **Open palm circling** → rotate the Fate Ring
  - **Closed fist** (held 280 ms) → confirm the front card
  - **Peace sign** → trigger souvenir countdown
- A 3-second animated tutorial plays on the first card to demonstrate the gestures
- Full **mouse and touch fallback** for every interaction (drag the ring, tap a card, click the camera button)
### Responsive layouts
- **Landscape (default)** — desktop, large displays
- **Portrait kiosk (≤540 px wide)** — auto-triggers for vertical public-screen projections (e.g. 420 × 900)
- Souvenir camera preview and postcard frame are both native 3:4 portrait
---
 
## Tech stack
 
- **Pure HTML + CSS + vanilla JavaScript** — no framework, no build step
- **MediaPipe Tasks Vision** (CDN) — hand gesture recognition
- **html2canvas** (CDN) — composite the souvenir postcard into a downloadable image
- **Google Fonts** — Cormorant Garamond (italic serif, mystical/editorial) + Inter (UI)
- Assets bundled locally (tarot illustrations, event flyers, Postcard frame, background music)
---
 
## Project structure
 
```
lucky-fortune-wall/
├── lucky-fortune-wall.html       # Single-page app — HTML + CSS + JS inline
├── images/
│   ├── back.jpg                  # Shared tarot card back
│   ├── {theme}-{role}.jpg        # 21 tarot card illustrations (7 themes × 3 roles)
│   ├── flyer-{theme}.jpg         # Event poster flyers
│   ├── souvenir-frame.webp       # Postcard decorative frame (transparent window centre)
│   └── camera-icon.webp
├── audio/
│   └── musicbox.mp3              # Ambient mystical background music
└── README.md
```
 
---
 
## Run locally
 
```bash
# From the project root, any static server works:
python3 -m http.server 8000
# then open http://localhost:8000/lucky-fortune-wall.html
```
 
Gesture features ask for **camera permission** after you click **Begin** (user-activation requirement). Decline it and the mouse / touch fallback takes over.
 
Chrome and Safari both work. Hand gestures are more reliable in good lighting.
 
---
 
## Design
 
- **Dark mystical palette** — deep navy background, gold accents, teal and coral highlights
- **Vintage pastel tarot illustrations** — generated for this prototype in a consistent hand-painted look
- **Typography** — Cormorant Garamond for titles and poems (italic serif, mystical), Inter for UI
- **Motion** — card bob + shimmer on the attract screen, 3D ring rotation, card-flash on confirmation, animated gesture tutorial, Connection page reveal
---
 
## Content notes
 
Event flyers reference real Newtown events as of **November 2026** (Newtown Street Party, Newtown Bakery Crawl, Annual Halloween Street Party, and others). Dates, venues and ticketing should be verified with the organisers — this is a prototype, not a live service. The content pipeline is intentionally simple: all event metadata lives in the `READINGS` object at the top of the `<script>` block.
 
The three *Hidden Places / Mystical* cards and the Library CTA for *The Borrowed Voice* are speculative content for research purposes.
 
---
 
## Iteration
 
Several rounds of informal user testing shaped the current design:
 
- **Gesture discoverability** — static icon labels weren't enough; replaced with a 3-second animated gesture tutorial that plays on the first card
- **Flow pacing** — the souvenir camera used to live inline on the reading page and felt crowded; it now has its own dedicated page
- **Shared adventure** — a simple tap-to-pick picker was replaced with a rule-based Connection analysis page that classifies the group (Shared Interest / Unexpected Harmony / Different Paths) and then a Choose Our Next Stop decision stage
---
 
## Acknowledgements
 
- Newtown event sources — Young Henrys · The Courty · @bakerycrawl.syd · Your Local · Enmore Theatre · Newtown Neighbourhood Centre · Inner West Council
- MediaPipe gesture recognition by Google
- Built with Claude Code
---
 
## Licence
 
Personal project. Not for commercial use. Please contact me before reusing code or assets.
 
