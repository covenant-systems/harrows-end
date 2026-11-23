# Harrow's End

A first-person survival horror game that runs in the browser.

You crash on a detour and end up in a small town that isn't on any map. Every road out loops back in. By day the town is empty. At night, human-shaped things come out of the trees, and the only safe place is a room with a talisman hanging by the door.

## Play

Open `index.html` in a desktop browser (Chrome, Edge or Firefox). You need a keyboard and mouse. If GitHub Pages is turned on for this repo, you can also play it at the Pages URL.

To run it locally with a server:

```
python -m http.server 8000
```

Then go to http://localhost:8000.

## Controls

| Key | Action |
| --- | --- |
| W A S D | Walk |
| Shift | Run (uses stamina) |
| Mouse | Look |
| E | Use, read, pick up (hold for some things) |
| F | Flashlight |
| M | Map (once you have one) |
| J / Tab | Journal: objectives and notes |
| T | Hold to wait for dawn while protected |

## How it works

- **Day and night.** A full day takes about 6 minutes, and night lasts about 2½ of them. A bell rings at dusk. More creatures come each night.
- **Talismans.** A room is safe only while a talisman hangs by its door. Creatures stop at the doorway, knock, and try to talk you into opening up. You can carry one talisman at a time and move it from room to room, but the room you take it from stops being safe.
- **The loop.** Walk out of town in any direction and you come back in from the other side.
- **The way out.** Hal's map in the diner marks four places in the woods. Each holds a relic:
  - **The bus:** find three carved figures and bring them back.
  - **The stones:** wake five glyph stones in the order a nearby note gives.
  - **The radio tower:** tune the receiver to her frequency (it changes every game) and listen to the end.
  - **The well:** it only gives after dark, and the crank draws every creature to you.

  Put all four relics in the waystone by the north sign, then walk the road north in daylight.
- **Dying.** If they catch you, you wake up in the diner the next morning. You keep your progress.

## Tech

A single `index.html` built with [three.js](https://threejs.org/) r128 (loaded from cdnjs). All models, textures and sounds are generated in code, so there are no asset files.

For testing, open the page with `#debug` on the end of the URL. That exposes the game state as `window.__he` in the browser console.
