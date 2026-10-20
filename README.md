# Killzone: Shadow Fall — Android

Experimental, title-specific PS4-to-Android ARM64 runtime adaptation.

## Foundation and thanks

This is a **heavily modified, game-specific adaptation of the God of War III Android runtime**, originally developed in [zFitness/gow3_android](https://github.com/zFitness/gow3_android). It is configured to run only the game named in this project. It is not a general-purpose PS4 emulator and is not intended to run God of War III or other games.

A huge thank you to **zFitness and all owners, maintainers, and contributors of the God of War III Android runtime**. Without their work, these two adaptations would not have been possible. Their runtime, Android integration, and graphics foundation made this work possible. Please support and credit the original project.

Credit also remains with the upstream projects and contributors used by that runtime, including FEXCore, shadPS4, and its other dependencies. Original copyright and license notices remain applicable. The upstream runtime is GPL-2.0-or-later; third-party components retain their respective licenses. These adaptations are independent work and are not official releases from the upstream authors or the game publishers.

## AI development and testing limits

These projects were **made with AI (ChatGPT/Codex)**, with human-guided development and testing on an Android phone. AI was used to help develop compatibility changes, diagnose logs, modify runtime and graphics code, and build and package the APKs.

**Only the first levels have been tested.** The full games have not been completed or validated. There may be bugs, crashes, rendering problems, or freezes later in the game. These are experimental alpha releases.

## Game files and device

No game executable or proprietary game-data files are included in these APK downloads. Supply your own legally obtained files for the supported game/version.

Testing was performed on a REDMAGIC 10S Pro running Android 16, with a Snapdragon 8 Elite Leading Version, Adreno 830, and 24 GB RAM. Vulkan/Turnip graphics are used. **The latest Rubataga / WinNative Turnip drivers are recommended for better performance.** Other devices and drivers are not comprehensively tested.

## What was changed for Killzone: Shadow Fall

- Adapted an isolated copy of the working Full Metal Panic Android runtime for **Killzone: Shadow Fall, PS4 CUSA00190 update 01.81**.
- Added game-specific executable preparation, dynamic-module/TLS handling, and PS4 compatibility fixes, including memory layout, content/PlayGo, and font/PNG handling.
- Extended the GPU hull-shader translator to handle **dynamic patch addressing**, addressing the `patch addr non imm` translation blocker. The shader implementation was adapted from the [Killzone Shadow Fall PC project by lesca-191204 and its contributors](https://github.com/lesca-191204/killzone-shadowfall-pc), with thanks to them as well.
- Reworked the Vulkan depth/color buffer-copy fallback to handle shared mip levels, array layers, and depth slices, replacing the single-mip/equal-layer assumption that stopped campaign loading.
- Implemented real PS4 touchpad contacts for the OWL drone: finger-down, moving coordinates, a stable finger ID, and finger-up. Corrected the native touch-count field offset and added a swipe area in the Android controls.

The user confirmed that the previous level-loading crash no longer occurred and that the touch area worked correctly. Extended campaign stability remains untested.

## Downloads in this release

- **Alpha 7.17 branding update:** `Killzone_Shadow_Fall_Android_Alpha7_17_KillzoneArtwork.apk` — the newer app icon/background packaging, using the same signing identity.

This is an experimental alpha release.

SHA-256 values are in `SHA256SUMS.txt`. APK signatures and archive integrity were checked before preparing this release.
