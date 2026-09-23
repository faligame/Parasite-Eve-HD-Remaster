<p align="center">
  <img src="media/logo.jpg" alt="Parasite Eve HD Remaster" width="820">
</p>

<p align="center">
  <b>A native PC version of Parasite Eve, rebuilt from the original PlayStation game and remastered in high definition.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/status-in%20development-2ee6d2?style=for-the-badge" alt="Status: in development">
  <img src="https://img.shields.io/badge/platform-Windows-1f6feb?style=for-the-badge" alt="Platform: Windows">
  <img src="https://img.shields.io/badge/fan%20project-non%20commercial-555?style=for-the-badge" alt="Fan project, non commercial">
</p>

<p align="center">
  <a href="README.es.md">🇪🇸 Leer en español</a>
</p>

---

## About the project

**Parasite Eve HD Remaster** brings Square's 1998 horror RPG to modern PCs. It is the sister project of
[Parasite Eve II HD Remaster](https://github.com/faligame/Parasite-Eve-2-HD-Remaster).

This is **not an emulator**. The original PlayStation game code has been statically recompiled into a native Windows
executable, which makes it possible to improve the game from the inside: sharp 3D models, stable geometry and
pre-rendered backgrounds rebuilt in high resolution.

This repository is the **public home of the project**: news, screenshots and progress. It contains no source code,
executables or game data.

> ⭐ **Star** the repo and hit 👁️ **Watch** to follow development.

---

## Proof of concept: the first HD background

The Carnegie Hall auditorium, the room where it all begins, is the first remastered background. It is the **whole
camera view**, larger than the screen (517×384 pixels in the original, scrolled by the camera): rebuilt from the game
data, upscaled in one piece with AI to 4653×3456 and handed back to the game tile by tile.

<table>
  <tr>
    <td align="center" width="50%"><img src="media/comparisons/01_patio_butacas.webp" alt="Carnegie Hall auditorium with Aya: original PS1 vs HD"><br><b>In game</b></td>
    <td align="center" width="50%"><img src="media/comparisons/02_fondo_completo.webp" alt="Whole auditorium background: original PS1 vs HD"><br><b>Whole camera background</b></td>
  </tr>
</table>

<p align="center">
  <img src="media/comparisons/02_carnegie_hall_detalle.jpg" alt="Stage and staircase detail: original vs HD" width="900"><br>
  <b>Stage detail: original (left) and HD (right)</b>
</p>

---

## Gallery

<table>
  <tr>
    <td width="50%"><img src="media/screenshots/01_titulo.jpg" alt="HD title screen"><br><b>Title screen, redrawn in HD</b></td>
    <td width="50%"><img src="media/screenshots/02_carnegie_vestibulo.jpg" alt="Carnegie Hall lobby in HD"><br><b>Carnegie Hall lobby</b></td>
  </tr>
  <tr>
    <td width="50%"><img src="media/screenshots/05_heavenly_gate.jpg" alt="Sewers in HD"><br><b>Sewers: HD background with its animated water</b></td>
    <td width="50%"><img src="media/screenshots/03_callejon.jpg" alt="Backstage alley in HD"><br><b>Backstage, with the foreground that hides Aya</b></td>
  </tr>
  <tr>
    <td width="50%"><img src="media/screenshots/04_aya_nina.jpg" alt="Aya and a girl, HD character textures"><br><b>Characters with their HD textures</b></td>
    <td width="50%"><img src="media/screenshots/06_dialogo_castellano.jpg" alt="Dialogue with the HD font"><br><b>HD font (here with the community Spanish translation)</b></td>
  </tr>
</table>

---

## Features

### 🖥️ Native PC version
- **Static recompilation** of the North American release (both discs) into a native Windows executable. No emulator.
- **Boots with OpenBIOS**, a free BIOS: Sony's BIOS is not needed.
- **High internal resolution rendering** for sharp 3D models.
- **PGXP geometry precision**: no more wobbling polygons or warping textures.
- **Precise polygon culling**: the PlayStation decides which faces are visible using whole-pixel coordinates, so Aya
  lost triangles when seen from afar. That decision is now made with sub-pixel precision and distant characters stay
  complete.

### 🎨 HD remaster
- **HD texture engine using the disc's own names.** Every image is recognised when it is uploaded to video memory and
  replaced by its HD version, named after the game's own entry (`m005_2_04.png` = room 5, section 2, image 4) instead
  of an unreadable hash.
- **Whole backgrounds rebuilt from the disc.** In Parasite Eve the backgrounds are not single images: the game builds
  them on screen from hundreds of 16×16 tiles and the camera scrolls across them, so every camera view has its own size
  (the Carnegie Hall auditorium is 517×384). The project reads each room's and camera's tile list from the game data
  and rebuilds the **whole background**, larger than the screen, without having to play.
- **The whole background is upscaled, not the tiles.** The complete background is remastered in one go, with all its
  context, and a tool puts every HD tile back in its exact place (verified pixel by pixel). No seams between tiles.
- **Foreground included.** The door frames, pillars and seats that hide Aya come from the same background tiles, so they
  go HD as well and keep covering her exactly as before.
- **Animated background elements.** Water, lights and doors are not part of the fixed background: the game paints them
  on top, frame by frame, with the same tiles. Every frame of every animation is rebuilt from the disc and remastered,
  so the movement stays in HD too.
- **Characters, enemies and objects.** Every model texture is read straight from the disc, with the real colours and
  depth the game draws it with, and remastered: Aya and her outfits, the people she meets and the creatures she fights.
- **Combat effects, by palette.** The acid, the lightning and the Parasite Energy blasts are 16-colour sheets that the
  game recolours as it draws them, so one HD image was not enough. Each sheet is remastered once per palette and the
  game picks the right one while it plays.
- **Palette fades are followed.** When the game fades a room to grey as combat starts, it does it by changing the
  palettes. The HD textures now follow that fade instead of staying bright.
- **The New York map**, its building textures and its place names, remastered as well.

### 🔤 Text and languages
- **HD dialogue font.** The 12×12 pixel letters are replaced by a real typeface rendered at eight times the size, with
  the game's own shadow and its coloured names.
- **The community Spanish translation is supported**, with its accents and its extra letters, and the HD font covers
  them all.
- **Editable texts.** Every line in the game (dialogues, menus, item names) can be exported, edited in a spreadsheet
  and put back, without touching the disc.
- **HD title screen.** The logo, the menu and their glow are rebuilt in high resolution, in English and in Spanish.

### ✨ Quality of life
- **Up to 8x internal resolution** (and FXAA antialiasing) for clean edges on the 3D models.
- **Fast boot**: the legal notice and the loads before it no longer make you wait.
- **Fast forward** by holding L2 on the pad, with an on-screen indicator.
- **Optional cheats** for infinite HP, infinite Parasite Energy, maximum Bonus Points and 4x EXP, each one on its own
  pad shortcut.

### 🛠️ Tools
- **Built for texture artists**: automatic dumps of every texture with its real colours, one-key capture of the current
  camera, hot reload of the pack while the game is running and one key to compare instantly with the original.

---

## Roadmap

| Status | Feature |
|:---:|---|
| ✅ | Native Windows executable (static recompilation, North American release, both discs) |
| ✅ | Boots with OpenBIOS (no Sony BIOS) |
| ✅ | High resolution rendering and PGXP geometry precision |
| ✅ | Precise polygon culling (distant characters stay complete) |
| ✅ | Development tools: on-screen panel, frame-by-frame pause, traces and dumps |
| ✅ | HD texture replacement engine with the disc's names |
| ✅ | Whole backgrounds of every room and camera rebuilt from the disc |
| ✅ | Whole-background upscaling with automatic tile placement, foreground included |
| ✅ | First HD background: Carnegie Hall auditorium |
| ✅ | Animated background elements (water, lights, doors) |
| ✅ | Complete HD background pack (every room and camera) |
| ✅ | Remastered characters, enemies and objects |
| ✅ | Remastered combat effects (one version per palette) and New York map |
| ✅ | HD dialogue font, editable texts and support for the community Spanish translation |
| ✅ | HD title screen |
| ✅ | Fast boot, fast forward and optional cheats |
| 🚧 | HD combat interface and menus |
| 🔜 | High resolution cutscenes |
| 🔜 | 16:9 widescreen, 60 FPS, fast loading and single disc (as in Parasite Eve II HD Remaster) |
| 🔜 | Installer that builds the game from your own discs, so no game data is ever distributed |
| 🔜 | Public release |

---

## News

**23-09-2026 — The whole game in HD: animations, characters, effects and text**
- **The HD background pack is complete**: every camera of every room, 2835 of the 2836 background images on the disc.
- **Animated elements included**: 2296 animation frames (water, lights, doors) rebuilt from the disc, remastered and
  handed back tile by tile.
- **Characters, enemies and objects remastered**: 257 model textures read from the disc with their real colours.
- **Combat effects and the New York map**: 698 sprites, remastered one version per palette so the game keeps
  recolouring them as it always did.
- **Text in HD**: a real typeface for the dialogues at eight times the original size, support for the community
  Spanish translation with all its accents, and a rebuilt HD title screen.
- **Nicer to play**: up to 8x internal resolution, FXAA, fast boot, fast forward on L2 and optional cheats.

**21-09-2026 — The project starts, and the first HD background**
- **The game runs as a native executable**: the North American release (both discs) is recompiled and already
  playable without an emulator, booting with a free BIOS.
- **Distant characters stay complete**: the precise polygon culling built for Parasite Eve II comes here too, where it
  was needed even more.
- **Backgrounds rebuilt from the disc**: every camera of every room is assembled at its real size from the game data,
  upscaled in one piece and each tile goes back to its place. The first one is the **Carnegie Hall auditorium**.
- **HD pack tools**: every texture identified by its disc name, dumps with real colours, camera capture, hot reload
  and one-key comparison with the original.

---

## FAQ

**Can I download it?**
Not yet. The project is in active development. Follow this repository to hear about the first release.

**Will I need the original game?**
Yes. You will need your own legal copy of *Parasite Eve* for PlayStation (North American release). Game data will never
be distributed.

**Is it an emulator?**
No. The game code runs natively on your PC after being recompiled from the original PlayStation executable.

**Is the source code available?**
Not for now.

---

## Credits

| Project | Author | Used for | License |
|---|---|---|---|
| [PSXRecomp](https://github.com/mstan/psxrecomp) | Matthew Stan | The PlayStation static recompiler and hardware-faithful runtime this version is built on | PolyForm Noncommercial 1.0.0 |
| [Parasite Eve decompilation](https://github.com/khasinski/parasite-eve-decomp) | khasinski and contributors | Documentation of the game's formats (rooms, backgrounds, textures), symbols and addresses | — |
| [OpenBIOS](https://github.com/grumpycoders/pcsx-redux) | PCSX-Redux project | Free BIOS the game boots with | MIT |
| [Beetle PSX](https://github.com/libretro/beetle-psx-libretro) | libretro, based on Mednafen | Accuracy reference used by PSXRecomp | GPL-2.0 |
| PGXP | iCatButler | Original geometry precision technique | — |
| [PlayStation Specifications (psx-spx)](https://psx-spx.consoledev.net/) | Martin "nocash" Korth and contributors | Hardware documentation | — |

Libraries: [SDL3](https://libsdl.org), [stb_image](https://github.com/nothings/stb) (Sean Barrett),
[libchdr](https://github.com/rtissera/libchdr) and [zlib](https://zlib.net).

HD Remaster pack and project: **faligame**.

---

## Legal notice

This is a non-commercial fan project and is not affiliated with, endorsed or sponsored by Square Enix.
*Parasite Eve* is a registered trademark of Square Enix Co., Ltd. All game content belongs to its respective owners.
This repository does not and will never contain game files, BIOS or copyrighted game assets.
