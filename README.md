<div align="center">

# Mikołaj Lubiak

Systems programmer. C and C++ for a living and for fun.  
Into OS internals, embedded Linux, real-time rendering, game engines, and profiling.  
Outside code: biking, chess, gym, open source, Fediverse.

[![Email](https://img.shields.io/badge/email-lubiak%40proton.me-1976D2?style=flat-square&logo=protonmail&logoColor=white)](mailto:lubiak@proton.me)
[![Website](https://img.shields.io/badge/website-lubiak.pages.dev-1976D2?style=flat-square&logo=firefox&logoColor=white)](https://lubiak.pages.dev/)
[![LinkedIn](https://img.shields.io/badge/linkedin-lubiak-1976D2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/lubiak/)
[![Codeberg](https://img.shields.io/badge/codeberg-mikolajlubiak-1976D2?style=flat-square&logo=codeberg&logoColor=white)](https://codeberg.org/mikolajlubiak)

[Resume](https://lubiak.pages.dev/resume.pdf) · [PGP key](https://keys.openpgp.org/search?q=lubiak%40proton.me) · [Signal](https://signal.me/#eu/nq4qY30m4xgeCZ7R5IGoSUGbBK0n8Jg1Axi0cxbl3zAQdo3ikJVFioC_didTHi_F) · [PeerTube](https://video.infosec.exchange/c/gall_anonim_/video-playlists)

</div>

---

<h2 align="center">Projects</h2>

| Project | What it does |
|---|---|
| [**terminal_animation**](https://github.com/mikolajlubiak/terminal_animation) ![stars](https://img.shields.io/github/stars/mikolajlubiak/terminal_animation?style=flat-square&color=1976D2&label=stars) | Converts video, GIFs, and images into colored ASCII art in the terminal at the source frame rate. A decoder thread pulls frames via OpenCV/FFMPEG and converts pixels to RGB-escaped characters; a separate render thread drives the FTXUI TUI. Both threads synchronized with mutexes. C++20. |
| [**vlkn**](https://github.com/mikolajlubiak/vlkn) | Vulkan 3D renderer and game engine in C++20. 13+ abstractions over the Vulkan API: physical/logical device, swap chain with auto-resize, multi-pass rendering (opaque geometry + point-light billboards + ImGui overlay), OBJ model loading with vertex deduplication, mipmapped textures with anisotropic filtering, up to 16 dynamic Blinn-Phong point lights, 6-DOF camera at 512 Hz, push constants, descriptor sets, fixed-timestep game loop. |
| [**gos**](https://github.com/mikolajlubiak/gos) | x86 OS from scratch. Stage 1 fits inside the 512-byte MBR and loads Stage 2 (a full C program) from disk via LBA-to-CHS conversion with retry logic. Stage 2 has a FAT12 driver (BPB parsing, FAT table traversal, root directory search, cluster-chain following) and loads the kernel. Custom `printf`, `memcpy`, `memset`, and string functions for 16-bit real mode. NASM + C (Watcom compiler). |
| [**pixelpin**](https://github.com/mikolajlubiak/pixelpin) + [**app**](https://github.com/mikolajlubiak/pixelpin-app) | Wearable ESP32 e-paper badge. The Flutter app converts an image to RGB565 and streams it over BLE using a custom binary protocol with text-based command framing and raw data streaming. ESP32 firmware accumulates chunks through a state machine into two 1-bit framebuffers, runs Floyd-Steinberg dithering to map each pixel to black, white, or red, then refreshes the 2.9-inch tri-color e-paper display. Enters deep sleep after 5 minutes. C++ + Flutter. |
| [**espcon**](https://github.com/mikolajlubiak/espcon) | Embedded game console engine on an ESP32-S3. Software 3D rasterizer (no GPU) loads OBJ meshes from on-chip LittleFS, runs model-view-projection, painter's-algorithm depth sorting, dot-product directional lighting, and pushes RGB565 frames to a TFT display over SPI at ~80 MHz. FreeRTOS for task management; GPIO buttons and ADC joystick with deadzone filtering. |
| [**vectng**](https://github.com/mikolajlubiak/vectng) | 2D game engine built from scratch around an Entity-Component-System (ECS) architecture. Components include TransformComponent, SpriteComponent, Animation, ColliderComponent, CollisionResolverComponent, GravityComponent, KeyboardController, ScrollComponent, and TileComponent. SDL2 + SDL_image. |
| [**physics_automata**](https://github.com/mikolajlubiak/physics_automata) | Interactive falling-sand physics simulation using cellular automata. Each cell carries a feature bitfield (Fluid / Solid / Gas / Moveable / Immovable). Every frame, movable solids fall straight down or diagonally with shuffled direction order; movable gases disperse downward in randomized directions. Mouse drawing with adjustable brush radius. Rendered via raylib OpenGL render texture updated each frame. |

---

<h2 align="center">Contributions</h2>

| Contribution | What I did | How it works |
|---|---|---|
| [**Intel® Cryptography Primitives #95**](https://github.com/intel/cryptography-primitives/pull/95) | Fixed a redundant pointer assignment in the SHA `hashUpdate` path | In a multithreaded environment, writing a shared pointer twice forces other cores to invalidate their caches for that address. The redundant write caused extra cache-line bouncing; removing it gives ~10% less CPU time and ~50% fewer instructions in multithreaded hashing workloads. 21 files changed. |
| [**FTXUI #938**](https://github.com/ArthurSonzogni/FTXUI/pull/938) | Added `SliderWithCallback` component to FTXUI, merged by maintainer | Extends `Slider` with a `std::function` callback that fires on every value change, so actions can run without polling. 4 files, 90 additions. |
| [**PagedOut! #6**](https://pagedout.institute/) | Published a technical article | Gynvael Coldwind's free-form hacker/systems-programming zine. |

