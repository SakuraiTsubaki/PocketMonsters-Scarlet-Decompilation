# Version Coverage

This document is the authoritative human-readable inventory of software versions targeted by the Pokémon Scarlet decompilation project. Machine-readable coverage lives in `manifests/version-matrix.json`.

## Primary target

**Ver. 4.0.0** is the current primary target. Historical software versions remain explicit comparison targets so changes are not flattened into the latest build.

## Official update line

| Status | Revision / update | Official US release date | Role / milestone | Local hashes |
| --- | --- | --- | --- | --- |
| Planned | 1.0.1 | 2022-11-10 | Historical comparison | Unverified |
| Planned | 1.1.0 | 2022-12-01 | Historical comparison | Unverified |
| Planned | 1.2.0 | 2023-02-27 | Historical comparison | Unverified |
| Planned | 1.3.0 | 2023-04-19 | Historical comparison | Unverified |
| Planned | 1.3.1 | 2023-05-24 | Historical comparison | Unverified |
| Planned | 1.3.2 | 2023-06-28 | Historical comparison | Unverified |
| Planned | 2.0.1 | 2023-09-12 | The Teal Mask milestone | Unverified |
| Planned | 2.0.2 | 2023-10-11 | Historical comparison | Unverified |
| Planned | 3.0.0 | 2023-12-13 | The Indigo Disk milestone | Unverified |
| Planned | 3.0.1 | 2024-01-31 | Historical comparison | Unverified |
| Planned | **4.0.0** | **2025-06-02** | **Primary current target; Nintendo Switch 2 visual/frame-rate changes** | **Unverified** |

Nintendo's public update history is the source for version numbers and dates in this table. Package hashes, file-tree digests, executable identities, and build-specific metadata are deliberately left unverified until measured from local research material.

## Base application

A base/unpatched application target is reserved, but its exact version/build identity is **not inferred** here. It will be recorded only after a local base application is measured and identified.

## Status vocabulary

- **Planned** — intended for investigation but local identity is not yet verified.
- **Verified** — identity and hashes confirmed from the intended local target.
- **Mapped** — executable/data layout documented.
- **In progress** — active source reconstruction.
- **Matched** — reconstruction verified against the target.
- **Reference only** — used for comparison but not a reconstruction target.

## Recording rules

1. Record exact revision/update information whenever known.
2. Prefer cryptographic hashes over filenames as identity evidence.
3. Do not commit retail game images, update packages, raw local dumps, or console keys.
4. Record regional/language/platform differences instead of assuming identical content.
5. Keep DLC milestones and update-specific changes attached to the version where they entered the software line.
6. Link version-specific findings to relevant documentation, manifests, tests, or verification issues.
