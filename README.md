# 160 Years Victoria 3

Inert baseline mod shell for Victoria 3 **1.13.11**. This repository is the authoritative project source. It contains metadata and project instructions only; it does not change gameplay. The installed vanilla game is a read-only reference.

## Project gates

- **Phase 0.6 — complete:** implement and statically review the shell.
- **Phase 0.7 — complete:** verify launcher registration, loading, vanilla campaign startup, logs, and save/load.
- **Phase 0.8 — complete:** create the reviewed baseline commit and verify the checkpoint bundle and manifest.

The approved Phase 0.5 Architecture Design and Baseline Mod Shell Contract govern this pass. Future gameplay changes need their own approved contracts and plans. The canonical public repository is hosted on GitHub at GeorgeZotos/160-years-victoria-3.

## Local loading evidence

The installed game executable contains the `pdx_mod_dlc_manager/pdx_mod_stubber.cpp` template for `.metadata/metadata.json` and the `pdx_mod_metadata.cpp` parser fields. Its loader strings reference the same metadata path. The launcher settings report version 1.13.11, the `--mod_stubber` entry point, `modPath: mod`, and loose-file mod support. The metadata format and launcher registration passed Phase 0.7 runtime verification.

The game-facing integration uses a directory junction under the game's user-data `mod` directory, targeting this repository as the single source tree. Do not edit launcher databases or configuration to register the mod.

## Initial Phase 0 DLC baseline

The initial Phase 0 baseline was recorded **2026-09-24** from the installed game's Steam app manifest, matching installed DLC descriptors, and launcher content-load state (`disabledDLC: []`). The ten DLCs below were installed, and none was recorded as disabled. The Phase 0.7 runtime check confirmed the enabled inventory matched this baseline.

| Steam ID | Installed DLC |
| --- | --- |
| 2071470 | Victoria II Remastered Soundtrack |
| 2071471 | American Buildings Pack |
| 2348450 | Melodies for the Masses |
| 2282100 | Voice of the People |
| 2366580 | Voice of the People Preorder |
| 2411230 | Dawn of Wonder |
| 2591240 | Colossus of the South |
| 2411231 | Sphere of Influence |
| 3174360 | Pivot of Empire |
| 3450170 | Charters of Commerce |

The shell has no DLC-specific content or dependencies on other mods.
