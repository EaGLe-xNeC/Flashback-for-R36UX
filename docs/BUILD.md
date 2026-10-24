# Flashback for R36UX — Build Guide

## Target
- Linux ARM64 (aarch64)
- R36 Ultra X — 1024x768
- ArkOS4Clone with PortMaster
- REminiscence 0.5.6

## Requirements
- Docker
- dockcross/linux-arm64-lts
- ARM64 SDL2, libmodplug and zlib development files
- stb_vorbis.c (included in the source)

## Build environment
The local WSL directory ~/r36-flashback-build/ contains:
- include/
- libs/

These dependencies are not bundled with the repository.

## Compilation
Run this command from the project root:

    sudo docker run --rm \
      -v "$PWD:/work" \
      -v "$HOME/r36-flashback-build:/build:ro" \
      -w /work \
      dockcross/linux-arm64-lts:latest bash -lc '
        mkdir -p /deps
        ln -s /build/include /deps/include
        ln -s /build/libs /deps/libs

        make -B -j2 \
          SDL_CFLAGS="-I/deps/include -I/deps/include/SDL2 -D_REENTRANT" \
          SDL_LIBS="-L/deps/libs -lSDL2" \
          MODPLUG_LIBS="-L/deps/libs -lmodplug" \
          ZLIB_LIBS="-L/deps/libs -lz" \
          LDFLAGS="-L/deps/libs -Wl,-rpath-link,/deps/libs"
      '

The local ARM64 development headers and libraries must be
prepared before running this command.

## Reproducing the build environment

The Docker command above was validated with a previously prepared
local ARM64 dependency directory.

It is not a fully self-contained build procedure. Before running
it on another computer, prepare compatible ARM64 SDL2, libmodplug
and zlib headers and libraries in:

    ~/r36-flashback-build/include/
    ~/r36-flashback-build/libs/

These dependencies must match the target ARM64 Linux environment.
They are not downloaded automatically by the build command.

The exact preparation and provenance of the original local
dependency bundle have not yet been fully documented.

## Recorded ARM64 build dependencies

The tested binary was compiled using the following ARM64
development libraries:

| Library | Identified version | SHA-256 |
| --- | --- | --- |
| SDL2 | 2.32.10 | `4fd539cd0e2b2dc883beb8dedffa1f85212276b34e51b2a8bf98b4f8fd4f5cb4` |
| libmodplug | Version not confirmed | `54e494273f144cdb549684b13d56829d2717c151ec452c16bfdc08b87e91957e` |
| zlib | 1.2.11 (library filename) | `981be324472bdf3519ca5b9275413d0a3924b182d27f12605b35da499a0f0b52` |

All three files were identified as AArch64 ELF shared libraries.
These hashes document the original local build inputs;
they are not download links or requirements for an identical
binary hash.

The release ZIP does not distribute these libraries.
Their exact original download sources have not been recorded.

## Output
The compilation generates an ARM64 executable named rs.
For PortMaster, it is installed as ports/reminiscence/fb.

## Licensing
See docs/LICENSING.md before redistributing binaries.
