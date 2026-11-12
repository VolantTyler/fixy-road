# Road Crew

A top-down road building and road repair game for the browser. One file, no installs, no accounts, no ads, works offline once loaded.

## Play it

Open `index.html` in any browser. That file is the whole game.

## Put it on the iPad's home screen (free, about 10 minutes, one time)

1. Make a free account at github.com.
2. Create a new **public** repository, for example `road-crew`.
3. On the repository page choose **Add file > Upload files**, drag in `index.html`, and commit.
4. Go to **Settings > Pages**. Under "Build and deployment" choose **Deploy from a branch**, pick `main` and `/ (root)`, and save.
5. After a minute the page shows the address, like `https://YOURNAME.github.io/road-crew/`.
6. On the iPad open that address in Safari, tap **Share > Add to Home Screen**. It now opens full screen like an app.

To update the game later, upload a new `index.html` over the old one.

## How it plays

| Tool | What it does | Level |
| --- | --- | --- |
| Road | Drag to draw a two-way road. Cross another road to make an intersection. | Easy |
| Big Road | Four lanes. Draw over a small road to widen it. | Medium |
| Bridge | Drag over water, or over another road for an overpass. Ramps are added at the ends. | Easy |
| Cone / Barrel | Drag along a lane to close it. Cars merge around, or take turns if only one lane is left. | Easy / Medium |
| Arrow | Flashing arrow board. Points toward the open lane by itself. | Medium |
| Closed | Barricade across the whole road. Cars find a detour. | Medium |
| Pothole | Makes a lane old, gray and broken. | Easy |
| Fix | Sends a crew: break up, pave black, paint new lines. | Easy |
| Erase | Removes cones, signs, roads (and water, on Hard). | Easy |
| Water | Paint rivers and ponds. | Hard |
| Move | Drag the map. Two fingers also move and zoom with any tool. | Easy |

**Levels**

- **Easy**: fewer tools. Roads slowly fade to gray but never break by themselves. Fix sets its own cones.
- **Medium**: all building tools. Roads wear out and potholes appear (at most 4 at a time).
- **Hard**: faster wear, up to 9 potholes, and the crew will not start until he has put out cones himself.

**Jobs** are optional challenges: build or repair, press GO, and get a number of cars across before the bar runs out. Building is never timed. Only the driving is.

**Gear button**: sounds on/off, voice on/off, fewer or more cars, and start a new map (tap twice).

The map saves itself in the browser on that device.

## Changing the game

The source lives in `src/`. `node build.js` glues it into `index.html`.

- `01_world.js` grid, road pieces, lanes, saving
- `02_sim.js` cars, routing, merging, flaggers, wear, repair crews
- `03_render.js` drawing
- `04_game.js` touch input, tools, sounds, voice, menus, Jobs
- `style.css`, `body.html` the buttons and screens

Easy numbers to tune are at the top of `02_sim.js`: `MAXCARS`, `WEAR_RATE`, `HOLE_CAP`, `CREW_T`.

`test/` holds browser checks that need Node and Playwright, for example `node test/jobs.js /tmp`.
