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
| 1 – 6 | Choose what to say in a conversation |
| F | Flashlight |
| R | Swap in fresh batteries |
| M | Map (if you can find one) |
| J / Tab | Journal: leads, what people told you, notes |
| T | Hold to wait for dawn while protected |
| N | Music on or off |

## Getting started

You wake up in your wrecked car on the road south of town at 2 p.m. Your flashlight and two spare batteries are in the trunk. The flashlight drains while it's on (a set of batteries lasts about one night), so you'll want spares: you can find them in the sheriff's office, the general store, the gas station and the Tanners' barn, and two of the townsfolk will give you some if you ask.

## The town

| Who | Where | Notes |
| --- | --- | --- |
| Sheriff Dale Boone | Patrols the road | Lives with his family in the Boone house |
| Marisol Boone | Runs the diner | Dale's wife; wrote the note on the counter |
| Eli Boone | Hangs around the chapel | Their son, 15 |
| Dr. Imogen Vance | The clinic | A surgeon; lives at the clinic |
| Abel and Ruth Tanner | The farm, east of town | With their kids June (9) and Pip (6) |
| Cormac Reilly | The Lantern (bar) | Lives there with his daughter Nessa |

Everyone keeps a daily routine: out to work in the morning, home before dark. They open and close doors as they go, glance at you as you pass, say hello, and shout at you to get inside if they catch you out at dusk. You can stay the night with any of them.

Talking to someone opens a menu: ask about getting out, about the things at night, about the other townsfolk, ask for a favor (coffee from Marisol makes running less tiring, bread from Ruth helps you get your breath back, Dale and Nessa hand over batteries, Eli shares a survival tip), or just chat. Options with something new to hear are marked.

The buildings have working doors, clear glass windows you can see through in both directions, porches, shutters, chimneys and furnished interiors split into rooms. The Boone house and the farmhouse have a living room with a kitchen and fireplace, and a bedroom behind. The sheriff's office has two fully enclosed barred cells. The diner has a kitchen behind the counter, the Lantern has a storeroom where the Reillys sleep, and the clinic has a waiting room and an exam room. There's also a general store, a gas station and a water tower. The barn, Hal Cobb's house, the chapel, the store, the gas station and the empty house have no talisman.

## Sound

All sound is generated in the browser. There's a low drone that darkens as night falls, sparse piano-like notes, and tremolo strings that rise when something is hunting you. During the day you hear birds; at night, crickets, owls, distant screams, laughter in the trees and twigs snapping behind you. Creature sounds come from where the creature is: knocks at the door, tapping on the glass, the Milkman's bottles, the Bride's humming. The crickets go quiet when one of them is close. Sound is muffled indoors, and you breathe hard when you're winded or being chased. Headphones help.

## The things at night

Most of them look like ordinary people with a smile that's too wide. Some you'll learn to recognize. Each one has its own look, its own way of hunting and its own voice at the door. The townsfolk will warn you about them, and the first time you see one, it goes into your journal.

| Creature | First night | What it does |
| --- | --- | --- |
| The Milkman | 1 | White uniform, cap, a crate of bottles. Walks a route door to door every night, rattling his bottles and offering a delivery. You hear the clink before you see him. |
| The Bride | 1 | Grey-hemmed wedding dress, veil, bouquet. Hums the wedding march. Slower than you, but once she has seen you she never gives up until morning. |
| The Boxer | 2 | Red gloves and trunks, guard up. Charges in bursts faster than you can run, then stops and bounces on his toes. Run while he's waiting for the bell. |
| The Twins | 2 | Two women in matching yellow sweaters. Move side by side and say everything twice. |
| The Gentleman | 3 | Top hat, tailcoat, cane. Slow and polite, but when he spots you he rings a bell and every creature nearby comes for you. |
| The Nurse | 3 | White uniform and cap. Claims Dr. Vance sent her. Faster than the rest. |

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
