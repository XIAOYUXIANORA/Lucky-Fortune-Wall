LUCKY FORTUNE WALL · V2
=========================
IDEA9202 A3 · Outdoor interactive installation prototype

HOW TO RUN LOCALLY (needed for hand gestures + camera)
-------------------------------------------------------
Hand gestures require HTTPS or localhost. Running from file:// won't work.

Mac / Linux:
  1. Open Terminal
  2. cd to this folder (the one with index.html)
  3. Run:   python3 -m http.server 8000
  4. Open:  http://localhost:8000

Windows:
  1. Open PowerShell or CMD
  2. cd to this folder
  3. Run:   python -m http.server 8000
     (install Python from python.org if not installed)
  4. Open:  http://localhost:8000

HOW TO USE
----------
- Click "Begin" to start. Music begins and the camera will ask permission.
- Allow camera to enable hand gestures. Deny to stay touch-only.
- Choose an interest (6 themes). "Hidden Places" offers two paths:
  * Quiet Corners (default) — parks and green spaces
  * Mystical Newtown (subpath) — tarot windows, crystals
- Draw 3 cards from the Fate Ring:
  * HAND GESTURE: draw a circle in the air to spin, hold still ~1s to pick
  * TOUCH/MOUSE: drag the ring to spin, click the front card to pick
- See your reading, final Fortune Reading, and Explore actions
- The Borrowed Voice CTA opens an in-site Library info page

TOP RIGHT BUTTONS
-----------------
  ♪  music on/off
  ✋  gesture on/off
  Back / Restart

NOTES
-----
- Music file: audio/musicbox.mp3 (1.7 MB)
- Images in images/ (22 tarot + 1 map + 4 flyers)
- First time opening gestures downloads ~10 MB MediaPipe hand model
- Chrome/Edge/Safari work best; Firefox has some MediaPipe limits
- The "Find the Listening Library" button opens the in-site info page
  for the group's proposed indoor installation
