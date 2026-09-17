# Tensi — One-Minute Experience Film — Build Notes

Source: the "TENSI — ONE-MINUTE EXPERIENCE FILM" storyboard (voiceover + scene
direction). Per direction: no real footage — every scene that called for
construction/site footage or screen recordings is built as a text/motion-graphic
or UI-mockup stand-in instead, in the same dark-teal/amber/off-white Tensi brand
used in `experience.html`.

Voiceover was generated locally via `hyperframes tts` (Kokoro, voice `am_michael`)
and its real spoken duration drives scene timing — each scene's actual length is
its VO duration plus a short pre-roll (visual establishes before speech) and
post-roll (settle before the transition). No music bed: none of the available
assets fit the "premium, cinematic, restrained" mood the brief calls for, so
narration runs without a score for now, same call made on Page 1.

Sync points within each scene are computed proportionally from character
position in the VO text against that clip's measured duration (Kokoro doesn't
expose word-level timestamps) — a close approximation, not frame-exact forced
alignment.

## Final schedule (seconds, global time)

| Scene | Content | Start | Duration | VO starts |
|---|---|---|---|---|
| A | Opening — kinetic type over a blueprint-grid field | 0.00 | 10.50 | 0.60 |
| B | Human ecosystem mosaic (4 role tiles) | 10.50 | 9.34 | 11.00 |
| C | DMS / AI reveal (drag-drop → extraction → register → publish) | 19.84 | 13.05 | 20.34 |
| D | Info reaches site (device notification, Revision B) | 32.89 | 7.28 | 33.39 |
| E | Dive transition into Collab (no VO, zoom-through) | 40.17 | 2.00 | — |
| F | Collab reveal — full dashboard tour | 42.17 | 7.51 | 42.57 |
| G | One connected workflow — markup + RFI | 49.68 | 5.77 | 50.08 |
| H | Bring it together — mosaic pays off | 55.45 | 5.37 | 55.85 |
| I | Close — word recap → Tensi wordmark, brand hold | 60.82 | 7.71 | 61.32 |

Total: ~68.5s.

## What stands in for footage

- Opening / mosaic: blueprint-grid background (reused from Page 1), labeled
  role tiles (Architect, MEP Engineer, Site Supervisor, Document Controller)
  with simple line icons instead of photos of people.
- DMS/AI: a restrained "Tensi DMS" panel mockup — drop zone, scan line,
  extracted-field highlights, a register table populating, a publish badge.
- Site notification: a simple device-frame mockup with a revision notification.
- Collab: a 4-panel dashboard mockup (Documents, Markup/PDF, Messages/RFI)
  with pop-forward emphasis per panel, then a markup-cloud + RFI-form sequence.
- Close: sequential word recap, then the same wordmark treatment as
  `experience.html`, ending on "One Tensi."

## Known simplifications vs. the full brief

- No real construction/office footage, no real screen recordings — per
  direction, everything above is a text/graphic stand-in.
- No music bed — narration only.
- Sync is proportional-by-character, not word-aligned to real phoneme timing.
- The brief's continuous single-camera-move feel (e.g. the iPad dive into
  Collab) is approximated with a scale/blur zoom-through transition, not an
  actual continuous 3D camera path.
