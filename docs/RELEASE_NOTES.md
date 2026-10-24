# Flashback for R36UX v1.0

## First Release — Release Candidate

Flashback for R36UX is an enhanced adaptation of
the REminiscence 0.5.6 engine, specifically developed
for the R36 Ultra X handheld.

Target device:
- R36 Ultra X
- 4.5-inch display
- 1024x768 resolution (4:3)
- ArkOS4Clone with PortMaster
- ARM64 architecture

## Enhancements

### Fullscreen Cinematics

Improved cinematic scaling to make better use of
the R36 Ultra X display.

Polygon-based cinematic sequences and special
animations have been enlarged.

The original game graphics and gameplay proportions
remain unchanged.

### Special Animations

Improved scaling for special sequences, including
the Stone pickup animation.

The special travel cinematic also received a scaling
modification. The sequence was reproduced successfully
in fullscreen on the R36 Ultra X.

### Restored Audio Cues

Restored the short musical cue used during certain
special item pickup sequences.

### Sega CD Voice Support

Supports spoken dialogue using the original
Sega CD VOICE.VCE file.

The commercial voice data is not included.

### FN Button Support

The FN button can be used to exit the game on
the tested R36 Ultra X configuration.

### PortMaster Integration

Includes a PortMaster-compatible launcher,
controller integration and configuration files.

Game progress is stored in a dedicated saves directory.

## Validation

The following tests have been completed:

- ARM64 executable launches successfully.
- Separate installation works on the R36 Ultra X.
- Initial image, audio and controller tests passed.
- Save-state creation was confirmed.
- Installation ZIP integrity was verified.
- ZIP extraction was verified using SHA-256 comparison.
- Executable permissions are stored in the ZIP.

- Private ZIP package was extracted and launched successfully on the R36 Ultra X.
- The ZIP installation passed initial video, audio, controller and FN-button tests.

## Known Limitations

- The specific Voyage scaling branch has not been independently instrumented or verified.
- Compatibility with other handhelds has not been tested.
- Compatibility with firmware other than ArkOS4Clone
  has not been verified.
- Full regression testing of every cinematic is pending.

## Installation

See docs/INSTALLATION.md.

Original Flashback game data and compatible music
files must be supplied separately.

## Credits

Original REminiscence engine:
Gregory Montoir
https://github.com/cyxx/REminiscence

Flashback for R36UX is an independent community
adaptation and is not an official Flashback release.

## Publication Status

This is a private release candidate.

Public distribution is pending clarification of
the REminiscence 0.5.6 redistribution terms
and bundled library licensing.

## Final subtitle fix — v1.0

- Restored captions that were previously cropped by fullscreen cinematic scaling.
- Cinematics remain fullscreen at 1024x768 when captions appear.
- Captions are displayed in an opaque black overlay at the bottom of the screen.
- No abrupt cinematic resizing when captions appear or disappear.
- Gameplay, music, Sega CD voices and controller behavior remain unchanged.
- Verified on the R36 Ultra X running ArkOS4Clone.
