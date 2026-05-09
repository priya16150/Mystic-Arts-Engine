🔮 Doctor Strange — Mystic Arts Engine
Real-time hand tracking AR experience powered by MediaPipe, bringing the Mystic Arts to your browser.

HTML5 JavaScript MediaPipe Canvas API

✨ Overview
Mystic Arts Engine is a single-file, browser-based augmented reality experience inspired by Marvel's Doctor Strange. Using your webcam and hand gestures, you can cast spells, summon shields, open portals, and unleash mystic energy — all rendered in real-time on an HTML5 Canvas with particle systems and additive blending.

No dependencies to install. No build tools. Just open and cast.

🎬 Demo
Open index.html via a local server (see Setup)
Click ⟐ AWAKEN ⟐
Allow camera access
Start casting spells with your hands! 🧙‍♂️
🖐️ Gesture Controls
Gesture	Effect	Description
☝️ Point (index finger only)	🔴 Mystic Trail	A glowing red Catmull-Rom spline follows your index fingertip, fading over 1 second
✋ Open Palm (all fingers extended)	🛡️ Mandala Shield	An intricate 8-fold sacred geometry shield with Elder Futhark runes, concentric rings, and rotating squares appears on your palm
✋ Palm Flat (parallel to ceiling)	🌫️ Mystic Smoke	Cyan smoke particles pour from every joint of your hand — fingertips, knuckles, palm, and wrist
✊ Fist	⚡ Spark Explosion	50 ballistic gold sparks burst from your fist with gravity and motion trails
👆👆 Both index fingers close	🌀 Sling Ring Portal	A rotating orange portal with wobbling rings and spark particles opens between your fingers
🎨 Visual Features
🔴 Mystic Trail (Index Finger)
Catmull-Rom spline interpolation for ultra-smooth curves
Triple-layer glow rendering (outer → mid → core)
All-red color scheme with soft fade-out over 1 second
Continuous path rendering for seamless lines
🛡️ Mandala Shield (Open Palm)
Elder Futhark runes (ᚠᚢᚦᚨᚱᚲ...) rotating on the outer ring
4 concentric rings with varying thickness and opacity
3 overlapping rotated squares with red glow shadows
Inner diamond (45° rotated square)
8-fold sacred geometry star — two counter-rotating layers
16 radial lines emanating from center
Inner rune arcs and dual triangles
Pulsing center eye with radial gradient
All rendered in deep red color palette
Instantly appears/disappears with hand detection
🌫️ Mystic Smoke (Palm Up)
Emits from 10 hand landmarks simultaneously (wrist, all fingertips, knuckle joints)
20 particles per frame for dense coverage
Upward-drifting cyan particles with rotation
Additive blending for ethereal glow effect
Radial gradient rendering per particle
Only triggers when palm is flat and parallel to the ceiling
⚡ Spark Explosion (Fist)
50 sparks per burst with randomized trajectories
Realistic gravity simulation (downward acceleration)
8-point motion trail per spark
Gold/white dual-layer rendering
400ms cooldown between bursts per hand
🌀 Sling Ring Portal (Both Hands)
Triggers when both index fingertips are within 120px
3 rotating rings with sinusoidal wobble
Purple void center with radial gradient
Orbiting spark particles along the ring circumference
Grows to 140px radius, shrinks when fingers separate
🌌 Background & HUD
Parallax star field — 300 stars with depth-based sizing and fading
Mirrored webcam feed at 35% opacity for natural interaction
HUD badges that glow cyan when each effect is active
FPS counter in bottom-right corner
"MYSTIC ARTS ENGINE" title with orange text-shadow, auto-fades on start
🛠️ Tech Stack
Technology	Purpose
HTML5 Canvas	All visual rendering (particles, trails, geometry)
MediaPipe Hands	Real-time 21-landmark hand tracking
MediaPipe Camera Utils	Webcam stream management
Vanilla JavaScript	Gesture detection, particle physics, animation loop
CSS	Glassmorphism HUD, backdrop blur, layout
Architecture
Single File (index.html)
├── CSS — Styling, glassmorphism, layout
├── MediaPipe CDN Scripts — Hand tracking ML model
└── JavaScript
    ├── Star Field Background (bgCanvas)
    ├── Gesture Detection Engine
    ├── Particle Systems
    │   ├── TrailPoint (Catmull-Rom spline)
    │   ├── SmokeParticle (radial gradient)
    │   ├── Spark (ballistic physics)
    │   └── PortalSpark (orbital motion)
    ├── Shield Renderer (sacred geometry)
    ├── Hand Skeleton Overlay
    ├── HUD Manager
    └── Main Animation Loop (requestAnimationFrame)
🚀 Setup
Prerequisites
A modern browser (Chrome recommended for best MediaPipe support)
A webcam
A local HTTP server (MediaPipe requires HTTP, not file://)
Quick Start
# Clone the repository
git clone https://github.com/Axshatt/DrStrangeEffect.git
cd DrStrangeEffect

# Start a local server (choose one)
python3 -m http.server 8080
# or
npx serve .
# or
php -S localhost:8080
Then open http://localhost:8080 in Chrome.

One-Click (if Python is installed)
git clone https://github.com/Axshatt/DrStrangeEffect.git && cd DrStrangeEffect && python3 -m http.server 8080
📁 Project Structure
DrStrangeEffect/
├── index.html      # Complete application (single file)
└── README.md       # This file
Everything is contained in a single HTML file — no build tools, no frameworks, no npm packages.

🎮 Tips for Best Experience
Lighting — Ensure good, even lighting for reliable hand tracking
Background — A plain background behind your hands improves detection
Distance — Keep hands 1–3 feet from the camera
Browser — Use Chrome or Edge for best MediaPipe performance
Gestures — Make deliberate, clear gestures for best recognition
Smoke — Hold your hand completely flat (like a table) with palm facing up
🔧 Customization
All effects can be tuned by modifying constants in index.html:

Parameter	Location	Default	Description
Trail fade time	TrailPoint.life	1000ms	How long trails persist
Shield max radius	updateShield()	200px	Maximum mandala size
Spark count	updateSparks()	50	Sparks per fist burst
Portal threshold	updatePortal()	120px	Distance to trigger portal
Smoke emit points	updateSmoke()	10 landmarks	Number of smoke sources
Star count	stars array	300	Background star density
📜 License
This project is open source and available under the MIT License.

👤 Author
Akshat Singh

GitHub: @Axshatt
🙏 Acknowledgments
MediaPipe by Google — Real-time hand tracking
Marvel's Doctor Strange — Visual inspiration
Elder Futhark runic alphabet — Shield rune characters
"The Mystic Arts is not a set of parlor tricks. It is the study of the source of all reality."
— The Ancient One
