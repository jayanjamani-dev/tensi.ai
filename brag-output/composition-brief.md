# Hyperframes Composition Brief: Tensi Investor Prep

## Objective
Create a short, polished brag video for the Tensi Investor Prep app — a self-built flashcard trainer for drilling 85 real, hard investor questions before a May 7 fundraise.

## Output
- Composition directory: `brag-output/composition/`
- Rendered video: `brag-output/brag.mp4`
- Format: landscape — 1920x1080
- Duration: ~22-23 seconds

## Source Material
- Project root: `/home/user/tensi.ai`
- Primary files read: `index.html` (body markup, `<script>` app logic, `:root` CSS custom properties for both themes)
- Product name: Tensi (Investor Prep)
- Tagline / strongest claim: "Investor Prep · May 7 · 85 Questions"
- Key UI or visual moment to recreate: the flip card (question front → answer + "Why They Ask This" back), the category tabs, the progress bar / done counter, and the "You're Ready." completion screen
- Copy that must appear verbatim:
  - "Investor Prep"
  - "May 7 · 85 Questions"
  - "What if I want 20% equity?" (category: Equity & Deal, difficulty: Hard)
  - "You're Ready."
  - "Every question practised. May 7 is yours."

## Creative Direction
- Tone preset: `polished`
- Creative direction: the quiet, focused ritual of prepping for the meeting that decides whether the round closes
- Interpretation: restraint over hype — few scenes, longer holds, confident pacing, mixed-case type, generous spacing, nothing aggressive
- Angle: this is a founder grilling themselves with the exact hardball questions a VC will ask, before walking into the room. The tension is real because the questions are real.
- Hook: the splash screen — logotype + "Investor Prep" + "May 7 · 85 Questions" settling in on the dark teal background
- Outro / punchline: the app's own completion screen — checkmark, "You're Ready.", "Every question practised. May 7 is yours."
- Avoid:
  - Generic SaaS language
  - Abstract filler visuals
  - Unrelated visual redesign

## Visual Identity
- Background: `#002022` (dark teal, dark mode)
- Text: `#F5F2EC` (warm off-white)
- Accent: `#FFCD00` (amber)
- Success accent: `#4ecba0` (green)
- Display font: Inter (weight 800 for logotype/headline) — bundled/auto-embedded family, write `font-family: 'Inter', sans-serif` directly
- Body font: Inter (400/500)
- Visual references from the project: the flip-card UI, the amber "si" accent inside the wordmark "ten**si**", the category tag + difficulty pill on the question card, the checkmark completion screen

## Storyboard
Use the storyboard in `brag-output/brag-plan.md` as the creative contract.

Scene summary:
1. Hook: the deadline — ~5s — logotype scale-in, "Investor Prep" eyebrow, "May 7 · 85 Questions" settles
2. Reveal: the hard question — ~6s — flip card with "What if I want 20% equity?" (Equity & Deal / Hard), simulated tap-to-flip reveals the answer + "Why They Ask This"
3. Highlight: drilling every category — ~6.5s — category tabs land as a group, progress bar fills, done counter ticks up
4. Outro: you're ready — ~5.5s — checkmark + "You're Ready." + "Every question practised. May 7 is yours." + small wordmark hold

## Audio
- Audio role: warm, steady confidence bed under a quiet, deliberate edit
- Audio arc: steady bed throughout at moderate-low volume, no drops or big swells until a gentle rise into the outro, then fade under the final hold
- Music: `assets/music/happy-beats-business-moves-vol-12-by-ende-dot-app.mp3` (copied into composition)
- Music treatment: starts at 0, volume ~0.3, holds steady, gentle swell approaching the outro, fades in the last ~1s
- Music cue guidance: bundled preset at `assets/music/cues/happy-beats-business-moves-vol-12-by-ende-dot-app.music-cues.md` (tempo ~110 BPM). Beat-lock candidates used: ~4.91s (scene 1→2 transition), ~8.74s strong cue (card-flip reveal), ~10.93s strong cue (scene 2→3 transition), ~13.11s strong cue (progress/counter payoff), ~17.47s strong cue (scene 3→4 transition), ~18.56s strong cue (checkmark/headline landing)
- Audio-reactive treatment: subtle — per-frame band data pre-extracted to `assets/music/audio-data.js` (30fps, 16 bands, first 23s) via the `hyperframes-creative` extraction script. Use it to let the amber logotype glow and the outro checkmark glow breathe gently with treble/overall amplitude. No waveform/equalizer visuals.
- Audio-coupled moments:
  - Scene 1 — date line settle (~4.9s) — soft accent
  - Scene 2 — card flip (~8.74s beat-locked) — reveal accent
  - Scene 4 — checkmark/headline landing (~18.56s beat-locked) — success accent
- SFX selection guidance: minimal but present (polished posture) — 3 total cues, low high-frequency-risk families for a smooth result
  - `assets/sfx/interface/drop_001.ogg` — hook date-line settle (gentle reveal)
  - `assets/sfx/impact/impactSoft_medium_002.ogg` — card-flip reveal (low-risk, warm, transient)
  - `assets/sfx/interface/bong_001.ogg` — outro checkmark/headline landing (warm, low-risk, soft reveal)
- SFX analysis guidance: see `.claude/skills/brag/assets/sfx/sfx-analysis.md` for per-file HF-risk ratings; all three chosen files are rated low/medium risk
- Exact SFX choice: as above — already matched to the implemented animation moments
- Audio files: music, cue presets, extracted audio-reactive data, and the three SFX files are copied into `brag-output/composition/assets/`

## Hyperframes Instructions
Composition built directly against `hyperframes-core` (composition contract), `hyperframes-animation` → `transitions/` (blur crossfade between scenes, per the "premium/luxury" mood), and `hyperframes-creative` → `references/audio-reactive.md` (subtle glow driven by pre-extracted band data). Multi-scene structure follows `hyperframes-animation/transitions/catalog.md`'s "Scene Template": scene divs are always-present absolutely-positioned siblings of the root (no per-scene `data-start`/`data-duration`), visibility driven entirely by one paused GSAP timeline on `window.__timelines["tensi-brag"]`. Root carries `data-duration` for total render length.

Requirements:
- Show at least one real UI element from the source project (flip card, category tabs, progress bar, completion screen) — done across scenes 2-4.
- Keep all text readable: hold every line at least to its reading-time floor before the transition that follows it.
- Keep the video within 15-25 seconds (target ~22-23s).
- Include the music bed and the three planned SFX cues.
- Cue metadata is a timing bias, not a hard rule — text settle timing was chosen for readability first, then the nearest strong cue/beat was picked for the accompanying SFX/accent within tolerance.
- Run `npx hyperframes check` before render.
