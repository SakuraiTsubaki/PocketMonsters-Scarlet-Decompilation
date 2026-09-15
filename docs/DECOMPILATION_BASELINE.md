# Decompilation Baseline

This document freezes the first working baseline for the Pokémon Scarlet decompilation effort.

## Scope

The project reconstructs Pokémon Scarlet code, data structures, scripts, resources, and behavior from independently obtained local research material. Retail game images, update packages, console keys, and other redistributable proprietary binaries are not committed.

The first reconstruction target is the latest officially documented software line, with historical revisions retained as comparison targets rather than overwritten.

## Version strategy

1. **Primary current target:** Ver. 4.0.0.
2. **Historical comparison targets:** every officially documented update from Ver. 1.0.1 through Ver. 3.0.1.
3. **Base application:** preserve a slot for the unpatched/base application once its local identity is verified; do not invent hashes or build identifiers.
4. **DLC-aware comparisons:** treat The Teal Mask and The Indigo Disk content boundaries explicitly when mapping data introduced by Ver. 2.0.1 and Ver. 3.0.0.
5. **Platform behavior:** record Nintendo Switch 2-specific behavior associated with Ver. 4.0.0 separately from content shared with Nintendo Switch.

## First-pass filesystem model

The first local research input is an **already-extracted** directory tree. At this stage, the project does not assume that names or layouts are understood.

Expected top-level evidence classes:

- `exefs/` — executable-side material when present in the local research tree.
- `romfs/` — resource/data-side material when present in the local research tree.
- other files/directories — retained in the inventory without forced classification.

`tools/inventory.py` records every regular file by relative path, size, and SHA-256. It also produces a deterministic tree digest from those records. Symlinks are ignored.

## Evidence ladder

A path, format, symbol, function, subsystem, or behavior moves through these states:

1. **Unverified** — hypothesis or placeholder.
2. **Observed** — present in a verified local target.
3. **Reproduced** — extraction/parsing/behavior can be recreated with documented tooling.
4. **Mapped** — structure and role are documented sufficiently for reconstruction.
5. **Matched** — reconstructed result has been checked against the intended target.

No guessed symbol name, field meaning, file format, or subsystem relationship is promoted to fact without evidence.

## Phase 1 — inventory and identity

- [x] Establish repository policy and ignore rules.
- [x] Freeze the official update matrix.
- [x] Add a deterministic local extracted-tree inventory tool.
- [ ] Run the inventory against a verified Scarlet target.
- [ ] Record file count, total size, tree SHA-256, and per-file hashes.
- [ ] Identify executable-side files without assigning speculative semantics.
- [ ] Identify major resource/data containers.

## Phase 2 — structural mapping

After a verified inventory exists:

- map executable modules/sections;
- map major RomFS directory families and containers;
- record compression/archive/container signatures;
- build file-type and extension statistics;
- compare Scarlet/Violet common and version-specific paths;
- select the first subsystem for source reconstruction.

## Phase 3 — source reconstruction

Reconstruction begins only after the relevant structure is observed. Decompiled functions and reconstructed data receive stable project names while original/unknown identifiers remain documented separately.

Initial priority order:

1. executable/module map;
2. core data/container readers;
3. tables and game-parameter formats;
4. scripts/events;
5. world/map data;
6. graphics/UI/audio metadata and pipelines;
7. online/event/update-specific data where reproducible.

## Repository boundary

Committed: source, scripts, schemas, manifests, hashes, metadata, documentation, recreated assets where appropriate, tests, and verification outputs that do not contain prohibited retail binaries.

Not committed: retail game images, update packages, console keys, decrypted proprietary executables copied verbatim, or raw local dumps.
