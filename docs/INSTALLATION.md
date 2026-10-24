# Flashback for R36UX — Installation Guide

> **Important:** The public repository does not yet include the `fb` executable or `libmodplug.so.1`. The installation instructions below apply to a complete release package, which is not yet available.

## Target device

- R36 Ultra X handheld
- 1024 x 768 display
- ARM64 Linux
- Tested on ArkOS4Clone with PortMaster

Other firmware versions have not been verified.

## Installation from source

The public GitHub repository is source-only and is not
a ready-to-run installation package.

1. Compile the ARM64 executable using `docs/BUILD.md`.
2. Open the ROMs partition of the R36 Ultra X SD card.
3. Locate the `ports` directory.
4. Copy the launcher and configuration files from `portmaster`
   into their corresponding locations under `ports`.
5. Copy the compiled `rs` executable to
   `ports/reminiscence/fb` and make it executable.
6. Supply compatible ARM64 runtime libraries. The launcher
   searches `ports/reminiscence/libs` for bundled libraries.
7. Supply the original game assets as described below.

Expected locations:

- `ports/Flashback for R36UX.sh`
- `ports/reminiscence/fb`
- `ports/reminiscence/rs.cfg`
- `ports/reminiscence/libs/libmodplug.so.1`

Other shared library dependencies must also be available
on the target system.

## Installation from a complete release archive

When an authorized public installer becomes available,
extract its contents into the `ports` directory of the
ROMs partition, preserving the directory structure.

The installer does not contain commercial game assets.
Do not overwrite existing save data unnecessarily.

## Game data

Create the following directories if needed:

- `ports/reminiscence/gamedata`
- `ports/reminiscence/music`
- `ports/reminiscence/saves`

Copy the required original Flashback DOS game data into
the `gamedata` directory.

For Sega CD speech, place a compatible `VOICE.VCE`
file with the game data.

For music playback, supply compatible Flashback MOD files,
including the music modules used by the enhanced cutscenes.

Game data, voice recordings and commercial music assets
are not distributed with this project.

## Launch

Open the Ports section in EmulationStation and launch
`Flashback for R36UX`.

The FN button exits the game on the tested R36 Ultra X.

## Configuration

The included `rs.cfg` enables special cutscenes,
including the Stone pickup animation.

The launcher uses the `saves` directory for save data.

## Troubleshooting

If the game does not start, check:

- The ARM64 executable is present and executable.
- The required Flashback data files are present.
- PortMaster is installed and functioning.
- SDL2 and other runtime dependencies are available.
- `libmodplug.so.1` is in `reminiscence/libs`.

Review `ports/reminiscence/log.txt` for errors.

## Compatibility

Tested on one R36 Ultra X running ArkOS4Clone.
Compatibility with other handheld models or firmware
distributions is not guaranteed.
