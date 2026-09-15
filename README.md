# Pocket Monsters Scarlet — Decompilation

![Status](https://img.shields.io/badge/status-phase_1_active-blue)
![Project](https://img.shields.io/badge/project-decompilation-blue)
![ROMs](https://img.shields.io/badge/ROM_binaries-not_included-success)

Decompilation and source-reconstruction project for **Pokémon Scarlet**.

## 🎯 Goals

- Reconstruct game code and data into readable, editable source form.
- Document executable structures, data formats, scripts, assets, and version differences.
- Keep analysis, tooling, metadata, and documentation reproducible.
- Preserve update/DLC differences instead of flattening everything into one latest-state view.
- Build a clean foundation for long-term reverse-engineering work.

## 🚧 Status

**Phase 1 is active: target identity and extracted-tree inventory.**

The official update line has been recorded, Ver. **4.0.0** is the primary current reconstruction target, and a deterministic local inventory tool is now present at `tools/inventory.py`. The next evidence milestone is a verified local Scarlet extracted-tree inventory followed by the first ExeFS/RomFS structural map.

See [Decompilation Baseline](docs/DECOMPILATION_BASELINE.md) and [Project Status](docs/PROJECT_STATUS.md).

## 🗂️ Scope

- Code and executable analysis
- Game data structures
- Scripts and event data
- Graphics and asset metadata
- Audio and resource formats
- Maps and world data
- Update and DLC differences
- Scarlet/Violet common vs. version-specific structure
- Tools, notes, manifests, tests, and verification data

## 📌 Repository policy

Retail game images, raw local dumps, update packages, console keys, and redistributed proprietary binaries are **not included**. The repository is intended for reconstructed source, metadata, manifests, hashes, tooling, analysis, tests, documentation, and other reproducible research outputs that can be shared safely.

## 🧭 Roadmap

- [x] Establish repository policy and baseline research workflow
- [x] Record official software update matrix
- [x] Add deterministic local extracted-tree inventory tooling
- [ ] Verify a local Scarlet target and record hashes/tree identity
- [ ] Map executable and data structures
- [ ] Begin source reconstruction subsystem by subsystem
- [ ] Compare Scarlet/Violet common and version-specific paths/data
- [ ] Expand automated verification and reproducibility workflow

## 📚 Documentation

| Document | Purpose |
| --- | --- |
| [Decompilation baseline](docs/DECOMPILATION_BASELINE.md) | First working target, evidence rules, and phase boundaries |
| [Project status](docs/PROJECT_STATUS.md) | Current stage, coverage, validation level, and next milestones |
| [Roadmap](docs/ROADMAP.md) | Recommended decompilation phases and long-term progression |
| [Version coverage](docs/VERSIONS.md) | Updates, target versions, hashes, and verification state |
| [Research guide](docs/RESEARCH_GUIDE.md) | Evidence, confidence, and research-recording workflow |
| [Verification guide](docs/VERIFICATION.md) | Standards for Observed, Reproduced, Mapped, and Matched results |
| [Repository structure](docs/REPOSITORY_STRUCTURE.md) | Intended long-term source, data, asset, tooling, and manifest layout |
| [Documentation hub](docs/README.md) | Entry point for format, executable, script, asset, version, and verification notes |

## 🧰 First tool

Run the inventory tool against an **already-extracted local research tree**:

```bash
python3 tools/inventory.py /path/to/extracted/scarlet -o out/scarlet-4.0.0.inventory.json
```

The output contains relative paths, file sizes, per-file SHA-256 values, section counts, and a deterministic tree SHA-256. `out/`, `dump/`, `dumps/`, retail images, and key material remain ignored by Git.

## 🧱 Repository structure

As verified project material is reconstructed, the repository will grow into areas such as `src/`, `include/`, `data/`, `assets/`, `tools/`, `tests/`, and `manifests/`. Empty directory trees are not created only for appearance, and platform-specific structure follows verified target evidence rather than another generation's layout.

See [Repository Structure](docs/REPOSITORY_STRUCTURE.md) for the full organization policy.

## 🔬 Research and verification

Research findings must identify the relevant target version/revision and clearly separate hypotheses from observed, reproduced, mapped, or matched results. Unknown names and structures stay unknown until evidence supports stronger labels.

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution rules, evidence expectations, commit guidance, and pull-request requirements.
