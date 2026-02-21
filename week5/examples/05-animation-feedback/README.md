# Week 5 - Animation + Feedback

## Core loop
Collect all coins to clear the level while avoiding spinning hazards. Grab the power-up for temporary invincibility.

## Run
From this folder:
- `python3 -m pip install -r requirements.txt`
- `python3 main.py`

## Controls
- Arrow keys / WASD: move
- `Space`: start / restart
- `F1`: toggle debug overlay (hitboxes)
- `R`: reset level
- `1`: toggle flash cue
- `2`: toggle screen shake cue
- `3`: toggle hitstop cue
- `4`: toggle particles cue
- `Esc`: quit

## In this week with rationale
- **Invincibility power-up:** lasts 5 seconds, protects player from hazards
  - Includes new idle animation, encourages player to pick it up
  - Includes new pick-up anim and sound, makes player feel powerful
- **Sfx:** coin pick-up ("clink"), hazard hit ("bump"), power-up (upward sweep)
  - Encourage player to collect coins and power-ups with satisfying audio feedback, but avoid hazards with harsh audio feedback
- **Revised vfx:** flash for hit and power-up changed to sprite shape rather than bounding box
  - Helps player easily identify important game state changes related to their player character

## Weekly tuning notes
- Power-up anim initially a simple pulse over 12 frames
  - was too similar to coin anim
  - used sine easing to make a heartbeat-like effect over 6 frames
- Powered anim initially the same as hurt
  - needed to differentiate them semantically
  - added new state for powered with its own anim frames
- Coin sound started at 800 Hz linear fade, felt like a "chit," too harsh
  - switched to exponential decay, closer to a clink
  - settled on 600 Hz, warmer and less piercing
- Hit sound: initially a 160 Hz sine, too similar to coin, not impactful enough
  - dropped to 60 Hz with exponential decay, punchy low bump
- Power-up sound "glissando" sweep started at 300 Hz → 900 Hz / 0.25 s, felt thin
  - settled on 40 Hz → 160 Hz / 1.5 s, slow low rumble feels weighty and rewarding
