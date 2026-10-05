# OpenValence

Open hardware and software for linear motion machines. One hub holds the
machine's state, any number of clients stay in sync with it, and every part
of the stack is here in the open.

Website: https://openvalence.org

## The parts

| Repo | What it is |
|---|---|
| [Valence](https://github.com/openvalence/Valence) | The protocol. Spec, registry, reference library, clients, tools, documentation. MIT, spec text CC BY 4.0. |
| [Nucleus](https://github.com/openvalence/Nucleus) | Firmware for the OSSM Flagship PCB (ESP32-P4 + ESP32-C6). Pure ESP-IDF. Quadrature on the LP core, measured to within 8 ns. Apache-2.0. |
| [Phosphor](https://github.com/openvalence/Phosphor) | The cross-platform client. Windows, macOS, Linux (Flatpak). Plugins, themes, a built-in simulator to try everything with no hardware. Apache-2.0. |
| [Kinetic](https://github.com/openvalence/Kinetic) | The motion engine: trajectory planning, waveform shaping, blend and stretch policies. Header-only C++ on Ruckig, deterministic across targets. Apache-2.0. |
| [Hardware](https://github.com/openvalence/Hardware) | The OSSM Flagship PCB and everything physical around it. KiCad. CERN-OHL-S-2.0. |
| [Isotope](https://github.com/openvalence/Isotope) | Accessory firmware for the ESP-NOW network around Nucleus. WIP. |
| [ButtplugIO](https://github.com/openvalence/ButtplugIO) | Fork of buttplugio/buttplug with the Valence hardware manager (branch `valence`). |

## Where things stand

The firmware homes a real rail, plays scripts, and talks to the client over
Wi-Fi, with Bluetooth as the fallback. Phosphor builds for all three desktop
platforms from one source. The protocol is pre-release: it changes through
RFCs, and the registry is the single source of every wire number.

Read the [spec](https://github.com/openvalence/Valence/blob/main/spec/SPEC.md)
first if you want to build a client or a machine. Read
[Phosphor's plugin contract](https://github.com/openvalence/Phosphor/blob/main/docs/PLUGINS.md)
if you want to add a control surface.

## How it's built

One person designs this and makes every decision; coding agents write most
of the code under that direction. The rules they work to are in the repos:
a written doctrine, a registry that owns every wire number, lint that fails
the build, tests on every change, and a bench where firmware has to move a
real motor before it counts as done. That's stated here so nobody has to
guess.

## Credits

The Advanced pattern generator in Nucleus and Phosphor comes from
[fray-d's OSSM-Lite](https://github.com/fray-d/OSSM-Lite) and stays under
its CERN-OHL-S-2.0 license. The stroke patterns come from
[theelims' StrokeEngine](https://github.com/theelims/StrokeEngine). Motion
planning rides on [Ruckig](https://github.com/pantor/ruckig).
