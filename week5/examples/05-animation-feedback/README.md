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

## Weekly tuning notes
- Power-up anim initially a simple pulse over 12 frames
  - was too similar to coin anim
  - used sine easing to make a heartbeat-like effect over 6 frames
