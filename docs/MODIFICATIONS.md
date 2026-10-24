# Flashback for R36UX — Modifications

## Upstream

Based on REminiscence 0.5.6 by Gregory Montoir.

Original repository:
https://github.com/cyxx/REminiscence

Upstream reference:
947a4dce261aacc4f6ec0c2c90cb9d7e37712c7b

## Modified Source Files

### cutscene.cpp

- Improved fullscreen scaling for polygon-based cinematics.
- Enlarged special cinematic animations.
- Added scaling adjustments for the Stone pickup sequence.
- Modified scaling of the special travel cinematic.

Note: The travel cinematic modification still requires
validation in its corresponding gameplay scene.

### game.cpp

- Restored a short musical cue for selected cutscenes.
- Added a music-track mapping for original DOS track ID 0x15.

### systemstub_sdl.cpp

- Added handling for SDL_CONTROLLER_BUTTON_GUIDE.
- Allows the FN button to exit the game on the tested
  R36 Ultra X controller configuration.

### rs.cfg

- Configured cinematic behavior for the R36 Ultra X.
- Enabled special Stone and Metro cutscene options.
- Disabled SEQ cutscenes.

## Additional Project Files

- PortMaster launcher for the R36 Ultra X.
- Installation documentation.
- Licensing and attribution documentation.
- ARM64 private test build.

## Compatibility

Target hardware:
R36 Ultra X, 1024x768, 4:3.

Tested firmware:
ArkOS4Clone.

Other devices and firmware have not been validated.

## Redistribution

Public redistribution is pending clarification of
the upstream licensing terms and bundled binary dependencies.

## PortMaster Launcher Review

The PortMaster launcher was reviewed and tested on
the R36 Ultra X running ArkOS4Clone.

Validated behavior:
- PortMaster control configuration is loaded.
- Game files are loaded from the expected directory.
- Game saves use a dedicated saves directory.
- The FN button exits the game.
- Control returns to EmulationStation after exit.

Known limitation:
- The launcher uses 'kill -9' with 'pidof gptokeyb'
  during cleanup. This can terminate other gptokeyb
  processes if they are running simultaneously.

The existing cleanup method was retained for v1.0
because it passed the tested configuration.

## Fullscreen cinematic subtitles

The original fullscreen modification enlarged the cinematic image but cropped
captions rendered beneath it.

The final implementation preserves the original fullscreen image and copies
the caption strip into a bottom overlay when caption pixels are present.

This avoids the abrupt changes in framing caused by the earlier experimental
adaptive-zoom implementation.

The modification is implemented in Cutscene::updateScreen() in cutscene.cpp.
