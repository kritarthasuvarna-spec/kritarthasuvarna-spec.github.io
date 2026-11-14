# Kritarth Suvarna — 3D Portfolio Site

Owner: Viskit (Kritarth K. Suvarna), 3D generalist + technical artist. Prefers terse, direct replies.
This site = 3D work only. UI/UX stays on Behance (behance.net/kritarthsuvarna1).

## Hosting
- GitHub repo: `kritarthasuvarna-spec/kritarthasuvarna-spec.github.io`, branch `main`, GitHub Pages from root.
- `.nojekyll` present (serve files as-is).
- Live URL: https://kritarthasuvarna-spec.github.io/ (repo renamed Nov 2026 for the clean root URL). All asset paths are relative.
- Static site, no build step. Edit `index.html`, commit, push. Pages redeploys in about a minute.

## Standing workflow: every content update
When Viskit says "add/upload/update X":
1. Compress the asset (see Media rules), then put it in the right folder.
2. Edit `index.html` in the right section.
3. **Always add a devlog entry** in `<section class="log">` → `.posts`. Newest goes first. Keep 3–6 posts and drop the oldest.
   ```html
   <article class="post rv"><div class="row"><span class="chip">New</span><time datetime="2026-11">Nov 2026</time></div><h3 class="h3">Title</h3><p>One short line.</p></article>
   ```
   Chips in use: WIP, Breakdown, News, New, Update.
4. Test locally: run `python -m http.server 8765` and check that no section scrolls sideways at 360, 768, 1024 and 1440 widths.
5. Commit with a clear message and push to `main`.

## Structure
- `index.html`: the whole site (inline CSS/JS).
- Sections, in order:
  - hero (3D hatchet viewer)
  - `#about`
  - `#work` (grid)
  - `#animation`
  - `#rigging`
  - services
  - `#experience`
  - `#tools`
  - devlog (`.log`)
  - `#contact`
- `img/`: webp images for the grid.
- `anim/`: animation clips mp4 plus jpg posters.
- `loops/`: character loop mp4s plus jpgs.
- `rig/`: character-rig and tentacle-rig mp4 plus jpg.
- `video/`: larger video files.
- `tools/`: plugin and FootNote images, footnote-demo.mp4.
- `model/Hatchet.json`: glTF with an embedded base64 buffer, converted to GLB in the page, plus 3 JPG textures.
- `brand/`: cube logo.
- Libraries: three.js 0.147.0 from jsdelivr (three.min.js, GLTFLoader, OrbitControls).

## Work grid rules
- A tile looks like this:
  ```html
  <a class="tile rv" data-cat="char|env|prop|hard" href="#work" data-images="img/a.webp|img/b.webp" data-captions="Final render|Wireframe"><div class="frame real" style="background:#3C3C3C"><img src="img/a.webp" alt="..." loading="lazy"><span class="view">View images</span></div><div class="meta"><h3 class="h3">Name</h3><span class="cat">Character</span></div></a>
  ```
- `tile feature rv` spans 2 columns. **Each group must fill complete rows of 3 cells** (a feature counts as 2).
- The first image in `data-images` is the thumbnail, and clicking a tile opens the gallery lightbox.
- Group headers are `<div class="ghead" data-group="...">`, and the filters hide them.
- Characters use a #3C3C3C background.
- Current order:
  - Characters: Bob (f), Frog, Spitter, Brute, Rock Golem.
  - Environments: Backrooms (f), Night Gas Station (Sex Education ref), The Desk, Rain at the Rex, Vena, Stylized Flooded Train (f), Lighthouse, Moonlit Temple (f), Vecna House.
  - Stylized props: Hatchet (f), Stylized Bow, Stylized Vehicles, Circus Props (f), Mage Staff, Dagger, Potion Bottle, Round Shield (f), Low-poly Weapon Set.
  - Hard surface & products: Qrill, Gravity Drinking Water, …

## Design system (keep it)
- Colors, inspired by Blind Squirrel but not a copy:
  - cream #FFFBF3
  - forest #1F2C24
  - olive #60753F
  - orange #FF8702
  - gold #F2B443
  - rust #B95B43
- Concept is UV islands: a cut top-left corner on big sections and on the orange buttons.
- Logo is the cube. Do NOT reintroduce the KS initials logo (rejected).
- Responsive: `.g12` collapses to 1 column at 900px or less, and the grid goes 2 columns at 900px or less and 1 column at 560px or less.

## Media rules
- Images → webp (around q80, max width about 1600px). For transparent PNGs, composite onto #3C3C3C first, or they turn black.
- Video → H.264 mp4 with `-preset veryfast -crf 26`, `-movflags +faststart`, no audio unless needed. Add a jpg poster.
- GitHub file limit is 100 MB per file, so keep each under 50 MB.

## Content facts
- Experience:
  - Xpress Gaming 2023 – 2026 (3D Generalist)
  - StudioCupcakes 2022 – 2023
  - ViaCreate Productions 2022
  - Toolbox Studios 2021 – 2022
- Tools section:
  - FootNote (Microsoft Store)
  - Reslot
  - Instancer
  - FigToShop (Figma Community)

## Pending / ideas
- Shipped games section, to sit after Experience. Viskit will provide the game names, store links, his role on each, and screenshots.
- Optional: custom domain.
