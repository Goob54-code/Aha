# MiniDoom — a tiny FPS

A very small first-person shooter that runs in any modern browser and is fully playable on mobile. It's a self-contained raycaster (Wolfenstein/Doom style) in a single `index.html` — no build step, no dependencies.

## Play

Just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

Press **PLAY** and clear the level of all 8 enemies before they wear down your health.

## Controls

**Desktop**
- Move: `W` `A` `S` `D` or arrow keys
- Look: move the mouse (click the canvas to lock the pointer)
- Shoot: left click or `Space`

**Mobile / touch**
- Move: left on-screen joystick
- Look: drag anywhere on the right side of the screen
- Shoot: the **FIRE** button

## How it works

- **Raycasting** renders the 3D walls from a 2D grid map using DDA, with fish-eye correction and distance shading.
- **Billboarded sprites** draw the enemies, depth-sorted and occluded against the wall z-buffer.
- **Hitscan shooting** with light aim assist picks the nearest enemy near your crosshair that isn't behind a wall.
- Enemies chase you when they have line of sight and damage you up close.

Everything lives in `index.html`.
