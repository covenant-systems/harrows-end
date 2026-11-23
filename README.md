# Harrow's End

A first-person survival horror game that runs in the browser.

You crash on a detour and end up in a small town that isn't on any map. Every road out loops back in. A handful of people live here, and none of them know how to leave. At night, human-shaped things come out of the trees, and the only safe place is a room with a talisman hanging by the door.

**Play it:** https://covenant-systems.github.io/harrows-end/

## Run it locally

Open `index.html` in a desktop browser (Chrome, Edge or Firefox). You need a keyboard and mouse. Or serve the folder:

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
| E | Talk, open and close doors, read, pick up (hold for some things) |
| F | Flashlight |
| M | Map (if you can find one) |
| J / Tab | Journal: leads, what people told you, notes |
| T | Hold to wait for dawn while protected |

## The town

| Who | Where | Notes |
| --- | --- | --- |
| Sheriff Dale Boone | Patrols the road | Lives with his family in the Boone house |
| Marisol Boone | Runs the diner | Dale's wife; wrote the note on the counter |
| Eli Boone | Hangs around the chapel | Their son, 15 |
| Dr. Imogen Vance | The clinic | A surgeon; lives at the clinic |
| Abel and Ruth Tanner | The farm, east of town | With their kids June (9) and Pip (6) |
| Cormac Reilly | The Lantern (bar) | Lives there with his daughter Nessa |

Everyone keeps a daily routine: out to work in the morning, home before dark. They open and close doors as they go. You can stay the night with any of them.

The buildings have working doors, porches, shutters, chimneys and furnished interiors: the sheriff's office has a cell, the clinic has an exam table, the Lantern has a bar and a fireplace, the farm has fields, a fence, a barn and a scarecrow. The barn, Hal Cobb's house, the chapel and the empty house have no talisman.

## How it works

- **Day and night.** A full day takes about 6 minutes, and night lasts about 2½ of them. People head home in the late afternoon; a bell rings at dusk. More creatures come each night.
- **Talismans.** A room is safe only while a talisman hangs by its door. Creatures can't cross that doorway; they knock and try to talk you into opening up, sometimes in the voice of someone you know. In a room without a talisman, a closed door won't stop them. You can carry one talisman at a time and move it from room to room.
- **The loop.** Walk out of town in any direction and you come back in from the other side.
- **Finding the way out.** Nothing tells you what to do at the start. You learn it from the townsfolk, from notes, and by stumbling onto things in the woods. Characters with something new to say are marked when you look at them, and everything you learn goes into your journal. The map belonged to a man who went missing, and you have to find it.

## Spoilers

<details>
<summary>The full path out</summary>

- Ask Marisol or Dale about leaving: they point you to **Hal Cobb's house**, which holds his map and notebook.
- Four places in the woods each hold a relic:
  - **The bus (NW):** June tells you about it. Return three carved figures hidden around it.
  - **The stones (NE):** Ruth tells you about them; Nessa or a note gives the order (eye, hand, moon, tooth, door).
  - **The radio tower (SW):** Eli tells you about it. Tune the receiver to the frequency written on the shack wall (it changes every game) and listen to the end.
  - **The well (SE):** Dr. Vance tells you about it. It only gives after dark, and the crank draws every creature to you. Bring a talisman for the shed.
- Abel, Cormac or Hal's notebook tells you about the **waystone** under the NOW LEAVING sign. Fill its four hollows, then walk the road north in daylight.
- If they catch you, you wake up in the diner the next morning. You keep your progress.

</details>

## Tech

A single `index.html` built with [three.js](https://threejs.org/) r128 (loaded from cdnjs). All models, textures and sounds are generated in code, so there are no asset files. Static geometry is merged by material into a handful of draw calls, and the forest and crops are instanced.

For testing, open the page with `#debug` on the end of the URL. That exposes the game state as `window.__he` in the browser console, including `__he.step(n)` to fast-forward the simulation by `n` frames.
