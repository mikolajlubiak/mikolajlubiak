<div align="center">

# Mikołaj Lubiak

**Senior Software Engineer · Embedded Linux & Systems**

I build low-level software that has to be correct, fast and secure: embedded Linux platforms and security-critical system services at work, and real-time renderers on my own time. Based in Warsaw, Poland.

[![Email](https://img.shields.io/badge/email-lubiak%40proton.me-1976D2?style=flat-square&logo=protonmail&logoColor=white)](mailto:lubiak@proton.me)
[![Website](https://img.shields.io/badge/website-lubiak.pages.dev-1976D2?style=flat-square&logo=firefox&logoColor=white)](https://lubiak.pages.dev/)
[![LinkedIn](https://img.shields.io/badge/linkedin-lubiak-1976D2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/lubiak/)

[About me](https://lubiak.pages.dev/about/) · [Projects](https://lubiak.pages.dev/projects/) · [PGP key](https://keys.openpgp.org/search?q=lubiak%40proton.me)

</div>

---

At **Xperi** I work on the security and provisioning side of a Linux-based smart-TV operating system, from the boot chain to the cloud: secure boot and device identity, factory and over-the-air provisioning, platform hardening and vulnerability response across the kernel and user space. I write C and C++ for the kernel, bootloader and system services, and Python for provisioning tools and automation.

Outside work I build things to understand how they work: Vulkan and software renderers, an x86 boot chain and firmware for microcontrollers.

---

<h2 align="center">Open source</h2>

| Contribution | What I did |
|---|---|
| [**Intel® Cryptography Primitives Library, PR #95**](https://github.com/intel/cryptography-primitives/pull/95) | Fixed a multithreaded cache-thrashing bug in SHA-1/SHA-2 hash dispatch, where a shared function pointer was rewritten on every call, and measured it with `perf`: −48% instructions, −32% cache references and −10% CPU time in a 12-thread SHA-256 benchmark. Intel shipped a fix for the issue in v1.4.0. |
| [**FTXUI, PR #938**](https://github.com/ArthurSonzogni/FTXUI/pull/938) | Added slider change callbacks (`SliderOption::on_change`) to this 10k-star C++ terminal UI library, shipped in v6.0. My terminal_animation app is listed in the project's showcase. |
| [**Paged Out! #6**](https://pagedout.institute/download/PagedOut_006.pdf#page=31) | "E Ink backpack pin/patch", a one-page article about my PixelPin build in the hardware section of this free technical zine. |

---

<h2 align="center">Projects</h2>

| Project | What it is |
|---|---|
| [**vlkn**](https://github.com/mikolajlubiak/vlkn) | A C++20 Vulkan renderer with a quaternion 6-DOF camera, an 8-slot texture sampler array with anisotropic filtering, Blinn-Phong lighting with 16 animated point lights, a fixed 512 Hz update loop and an ImGui debug overlay, built on swap-chain recreation (MAILBOX with FIFO fallback), two frames in flight synchronized with fences and semaphores, staging-buffer uploads, depth buffering, descriptor sets and push constants. |
| [**espcon**](https://github.com/mikolajlubiak/espcon) | A real-time 3D renderer for an ESP32-S3 with no GPU: hand-written vector and matrix math, back-face culling, flat lighting and painter's-algorithm depth sorting, with triangles filled over 40 MHz SPI on ST7735/ILI9341 TFTs and OBJ meshes streamed from a LittleFS partition in flash. An analog joystick and buttons drive the camera. |
| [**pixelpin**](https://github.com/mikolajlubiak/pixelpin) + [**app**](https://github.com/mikolajlubiak/pixelpin-app) | A wearable ESP32 e-paper badge. The firmware runs a custom BLE GATT protocol that streams an image in 512-byte chunks into two 1-bit framebuffers (black and red planes) and drives a 2.9-inch black/white/red panel, deep-sleeping when idle and waking on a GPIO pin (ESP32-C3). A Flutter app rotates, crops, dithers and packs images on the phone. Written up in Paged Out! #6. |
| [**coneng**](https://github.com/mikolajlubiak/coneng) | A software 3D renderer: the whole triangle pipeline runs on the CPU, with matrix math, back-face culling, near-plane and screen-edge clipping, flat shading, perspective-correct texture mapping with a 1/w depth buffer, and OBJ loading. olcPixelGameEngine only presents the finished frame. |
| [**gos**](https://github.com/mikolajlubiak/gos) | A two-stage x86 boot chain: a 512-byte NASM boot sector walks a FAT12 filesystem to load a 16-bit real-mode C second stage with a freestanding mini libc and a FAT12 driver, using BIOS disk services with retries. Debugged in QEMU and Bochs. |
| [**terminal_animation**](https://github.com/mikolajlubiak/terminal_animation) ![stars](https://img.shields.io/github/stars/mikolajlubiak/terminal_animation?style=flat-square&color=1976D2&label=stars) | Plays video, GIFs and images as 24-bit color ASCII art in the terminal. A decode thread converts frames into colored character cells while a pacing thread drives the FTXUI interface at the source frame rate; shared state is guarded by mutexes and atomics. C++20, builds on Linux and Windows. |
| [**physics_automata**](https://github.com/mikolajlubiak/physics_automata) | Falling-sand physics on a cellular automaton (movable solids, gas and walls) in C++ with raylib, compiled to WebAssembly with Emscripten. [Try it in the browser](https://lubiak.pages.dev/physics_automata/) (best on a desktop with a mouse). |

More on [lubiak.pages.dev/projects](https://lubiak.pages.dev/projects/).
