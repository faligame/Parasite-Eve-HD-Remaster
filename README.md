<!-- LOGO: the Parasite Eve HD Remaster logo goes here (media/logo.png), like the Parasite Eve II HD Remaster banner:
<p align="center">
  <img src="media/logo.png" alt="Parasite Eve HD Remaster" width="820">
</p>
-->

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

<p align="center">
  <img src="media/comparisons/01_carnegie_hall.jpg" alt="Carnegie Hall auditorium: left half original PS1, right half HD" width="900"><br>
  <b>Left half: original PS1 · Right half: HD Remaster</b>
</p>

<p align="center">
  <img src="media/comparisons/02_carnegie_hall_detalle.jpg" alt="Stage and staircase detail: original vs HD" width="900"><br>
  <b>Stage detail: original (left) and HD (right)</b>
</p>

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
| 🚧 | Animated background elements (lights, doors) |
| 🚧 | Complete HD background pack |
| 🔜 | Remastered characters, enemies and weapons |
| 🔜 | High resolution cutscenes |
| 🔜 | 16:9 widescreen, 60 FPS, fast loading and single disc (as in Parasite Eve II HD Remaster) |
| 🔜 | Installer that builds the game from your own discs, so no game data is ever distributed |
| 🔜 | Public release |

---

## News

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
