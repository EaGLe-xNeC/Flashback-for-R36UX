# Flashback for R36UX

> **Pre-release:** This repository currently contains source code and PortMaster configuration, but no prebuilt executable or runtime libraries. Licensing review and release packaging are still in progress.

An enhanced adaptation of the REminiscence engine for the R36 Ultra X handheld.

## About

Flashback for R36UX is a community modification of REminiscence, the open-source reimplementation of the engine used by Flashback (1992).

This adaptation targets the R36 Ultra X handheld with a 4.5-inch, 1024x768 display and ArkOS4Clone.

## Features

- Fullscreen cinematic sequences optimized for the R36 Ultra X display.
- Improved scaling for special cinematics, including the Stone pickup animation.
- Restored musical cues for item pickup sequences.
- Sega CD voice support through the original VOICE.VCE file.
- Working FN button to exit the game.
- PortMaster launcher and controller integration.
- Preserved gameplay proportions and adjacent-room widescreen rendering.

## Requirements

- R36 Ultra X handheld
- Compatible Linux firmware with PortMaster support
- Original Flashback game data files
- Optional Sega CD VOICE.VCE file for spoken dialogue
- Compatible music modules for the soundtrack

Commercial game assets are not included.

## Installation

1. Copy the contents of the `portmaster` directory to your ROMs partition's `ports` directory.
2. Place your legally obtained Flashback game data in `ports/reminiscence/gamedata`.
3. Place compatible music modules in `ports/reminiscence/music`.
4. Launch `Flashback for R36UX` from the Ports menu.

See the installation guide for additional details.


## Screenshots

### Gameplay
![Gameplay](screenshots/gameplay.png)

### Cinematics
![Cinematics](screenshots/cinematics.png)

### Special Animations
![Special Animations](screenshots/special-animations.png)


## Build

The included source was cross-compiled for Linux ARM64 using Docker and the dockcross Linux ARM64 toolchain.

The build requires SDL2, libmodplug and zlib development libraries compatible with the target system.

## Credits

- Gregory Montoir — original REminiscence engine.
  https://github.com/cyxx/REminiscence
- Alex Chermenin — REinforced, a related enhanced REminiscence project.
  https://github.com/chermenin/REminiscence
- Jetup13 — REminiscence-oga, a related adaptation for Linux handhelds.
  https://github.com/Jetup13/REminiscence-oga

Flashback and its original game assets belong to their respective rights holders.

## Status

Version 1.0 — based on the tested R36 Ultra X v13 build.

The special travel cinematic scaling change has not yet been validated in its specific scene.

## License

License information and redistribution terms are being verified before public release.
