# 160 Years Victoria 3

A Victoria 3 timeline-extension project for **Victoria 3 1.13.11**.

The long-term goal is to extend the playable timeline beyond the vanilla 1936 endpoint toward the modern era, while preserving the vanilla **1836–1936** experience as much as practical.

The repository is the authoritative project source. Vanilla game files are treated as read-only reference material, and gameplay changes are implemented additively wherever possible.

## Current status

### Phase 0 — Foundation: COMPLETE

- **Phase 0.6:** baseline mod shell implemented and statically reviewed.
- **Phase 0.7:** launcher registration, game loading, vanilla campaign startup, logs, and save/load runtime-tested.
- **Phase 0.8:** baseline checkpoint created, published, and recovery-archived.

### ERA I — 1936–1945

- **ERA I / 1.1 — Starting-State Bridge: COMPLETE**
  - Vanilla campaign start remains `1836.1.1`.
  - Campaign end moved from `1936.1.1` to `1946.1.1`.
  - No historical 1936 reset or alternate starting scenario was added.
  - No vanilla files were modified.
  - No `replace_path` is used.
  - No unrelated gameplay content was introduced.

Runtime validation on Victoria 3 **1.13.11** confirmed:

- normal continuation through `1936.1.1` without GAME OVER;
- continued control of the same campaign state;
- successful post-1936 save/load;
- GAME OVER at the new endpoint, `1946.1.1`;
- continuation and save/load around the new endpoint;
- no material bridge-attributable runtime or encoding errors.

The next planned development pass is:

**ERA I / 1.2 — Technology**

## Development approach

The project follows an additive-first preservation strategy:

**REUSE → RETIME → REPURPOSE → EXTEND → ADD**

The aim is to preserve vanilla systems and content unless a later-era requirement explicitly requires a change.

Major gameplay changes are developed as small, reviewable passes with separate audit, design, implementation, review, runtime validation, and checkpoint stages.

## Local loading architecture

The game-facing installation uses a directory junction under Victoria 3's user-data `mod` directory, pointing to the authoritative repository as the single source tree.

This avoids maintaining a second copy of the mod.

The metadata format and launcher registration were verified during Phase 0 runtime validation.

## Initial Phase 0 DLC baseline

The initial Phase 0 baseline was recorded **2026-09-24** from the installed game's Steam app manifest, installed DLC descriptors, and launcher content-load state.

The following DLCs were installed and enabled during the baseline validation:

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

The mod currently has no DLC-specific gameplay content and no dependencies on other mods.
