# Project instructions

- Treat the repository root as the authoritative Git working tree. Treat the installed Victoria 3 game files as a read-only vanilla reference. Never edit vanilla or copy its files into this repository merely as a baseline.
- Follow the approved Master Workflow, Phase 0.5 Architecture Design, and Baseline Mod Shell Contract. Implement gameplay work only under a current approved contract and plan. Keep passes small and reviewable.
- Preserve vanilla 1836–1936 behavior by default. Prefer additive files and unique project-prefixed identifiers where the game supports them. Never introduce `replace_path`, a same-path override, or a vanilla identifier override without explicit evidence and approval.
- Do not add end-date, era, technology, economy, country, history, UI, balance, or other gameplay changes during the baseline-shell pass.
- Current baseline: Victoria 3 1.13.11, with the initial installed DLC inventory recorded in `README.md`. If the game version or established enabled-DLC baseline changes, apply the Vanilla Update / Rebase Gate before affected implementation continues.
- Keep logs, caches, saves, launcher state, secrets, and machine-local artifacts out of Git. Do not directly edit launcher databases or configuration to force registration. The game-facing integration must keep this repository as the single source tree.
- Phase 0.6 ends with static review readiness and no commit. Phase 0.7 owns launcher and runtime QA. Phase 0.8 owns the clean commit, bundle, manifest, hashes, and verification.
