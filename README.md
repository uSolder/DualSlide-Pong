# Pong

Calm, modern Pong for one or two players.

A DualSlide game, built as a `.dsg` game file.

## Building

Needs the [DualSlide](../DualSlide) repository beside this one (it holds the
game SDK), the Arm GNU toolchain (`arm-none-eabi-gcc`), CMake, Ninja and
Python 3.

    cmake --preset default
    cmake --build --preset default

This writes `build/pong.dsg`.

## Installing

Connect the DualSlide to a computer, copy `pong.dsg` onto the DUALSLIDE
drive, and eject the drive.

## Details

| | |
| --- | --- |
| Identifier | `dualslide.pong` |
| Version | 1.0.0 |
