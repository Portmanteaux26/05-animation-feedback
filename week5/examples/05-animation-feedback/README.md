# Week 5 - Animation + Feedback

## Core loop
Collect all coins to clear the level while avoiding spinning hazards. Grab the power-up for temporary invincibility.

## Run
From this folder:
- `python3 -m pip install pygame`
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

## In this week
- **Invincibility power-up:** lasts 5 second, protects player from hazards
- **Sfx:** coin pick-up ("clink"), hazard hit ("bump"), power-up (upward sweep)

## Weekly tuning notes
- Power-up anim initially a simple pulse over 12 frames
  - was too similar to coin anim
  - used sine easing to make a heartbeat-like effect over 6 frames
- Coin sound: started at 800Hz/0.08s linear fade, felt like a "chit", too harsh
  - switched to exponential decay, closer to a clink
  - settled on 600Hz, warmer and less piercing
- Hit sound: initially tried 160Hz sine, too similar to coin, not impactful enough
  - dropped to 60Hz with exponential decay, punchy low bump
- Power-up sound: "glissando" sweep started at 300Hz→900Hz/0.25s, felt thin
  - settled on 40Hz→160Hz/1.5s, slow low rumble feels weighty and rewarding
