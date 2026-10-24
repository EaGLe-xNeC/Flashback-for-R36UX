# Flashback for R36UX — Installation Guide

## Target device

- R36 Ultra X handheld
- 1024 x 768 display
- ARM64 Linux
- Tested on ArkOS4Clone with PortMaster

Other firmware versions have not been verified.

## Install

1. Open the ROMs partition of your SD card.
2. Locate the `ports` directory.
3. Copy the contents of this project's `portmaster` directory into `ports`.
4. The game launcher should be located at:
   `ports/Flashback for R36UX.sh`
5. The executable should be located at:
   `ports/reminiscence/fb`

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
