# Project Status

**Current stage:** Phase 1 — target identity and extracted-tree inventory

The repository has moved beyond initial setup. The current task is to establish reproducible identity and filesystem evidence for verified local Pokémon Scarlet targets before assigning semantics to executable modules, data containers, or symbols.

## Version inventory

| Target | Role | Verification | Notes |
| --- | --- | --- | --- |
| Ver. 4.0.0 | Primary current target | Planned / local identity unverified | Officially documented latest Scarlet/Violet software update |
| Ver. 1.0.1–3.0.1 | Historical comparison line | Planned / local identity unverified | Preserve update-specific behavior and data changes |
| Base application | Baseline | Planned / identity unverified | Populate only after local measurement |

See `docs/VERSIONS.md` and `manifests/version-matrix.json` for the full matrix.

## Phase 1 progress

- [x] Establish repository policy and ROM/key exclusion rules.
- [x] Record the official software update line.
- [x] Select Ver. 4.0.0 as the primary current target.
- [x] Add deterministic extracted-tree inventory tooling.
- [ ] Run the inventory on a verified local Scarlet target.
- [ ] Record file count, byte count, tree SHA-256, and per-file hashes.
- [ ] Identify executable-side files and major resource/data containers.
- [ ] Produce the first executable/resource structure map.

## Long-term progress

- [ ] Document executable and section layout.
- [ ] Map symbols, functions, and major subsystems.
- [ ] Document game-data formats and resource containers.
- [ ] Reconstruct scripts, events, and behavior.
- [ ] Reconstruct asset pipelines and metadata.
- [ ] Add reproducible parsing/repacking tooling where appropriate.
- [ ] Add automated verification and regression tests.
- [ ] Compare Scarlet and Violet common/version-specific structures.

## Validation levels

- **Unverified** — proposed or recorded but not independently checked.
- **Observed** — confirmed directly in a target build or extracted data.
- **Reproduced** — behavior or data can be recreated with documented steps.
- **Mapped** — structure and purpose are documented sufficiently for reconstruction.
- **Matched** — reconstructed output is verified against the intended target.

## Immediate next milestone

Generate the first real extracted-tree inventory with `tools/inventory.py`, then use that evidence to create the initial ExeFS/RomFS structural map. No function, field, or container semantics should be guessed ahead of that evidence.
