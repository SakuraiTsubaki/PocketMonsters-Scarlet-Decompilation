# Generation IX Decompilation Toolchain

This repository uses a pinned local toolchain for Pokémon Scarlet reverse engineering and runtime validation. Tool binaries and emulator builds live under `.local-tools/` and are not committed.

## One-command bootstrap

From the repository root:

```bash
bash tools/bootstrap_gen9_linux.sh
source .local-tools/env.sh
python tools/verify_toolchain.py
```

The bootstrap installs or prepares:

- **Ghidra 12.1.3** — AArch64 disassembly/decompilation and headless analysis.
- **LLVM/Clang + AArch64 GNU binutils** — executable, section, symbol and instruction inspection.
- **Python analysis environment** — Capstone, LIEF, pyelftools, Construct, Kaitai Struct runtime, Rich and xxHash.
- **.NET SDK 10.0.401** — required by current pkNX and compatible with the pinned Ryubing source.
- **pkNX** at a pinned commit — secondary Generation IX format/data research reference. Its findings are not treated as ground truth without independent evidence.
- **Ryubing / Ryujinx** at a pinned source commit — built locally for runtime validation of user-owned game material.
- Compression/build utilities including zstd, lz4, CMake and Ninja.

The exact pins are recorded in `tools/toolchain.lock.json`.

## Emulator boundary

The repository installs/builds the emulator software only. It does **not** download or redistribute Nintendo Switch keys, firmware, games, update packages, DLC, NSP/XCI/NCA files or decrypted game dumps. Those inputs must come from the researcher's own lawful hardware/material and remain outside Git.

Runtime testing requires a local workstation with suitable GPU/Vulkan support. GitHub Actions is used for project/tooling tests, not for booting retail games.

## Optional bootstrap switches

Set any of these to `1` before running the script when a component is already managed externally:

- `GEN9_SKIP_SYSTEM=1`
- `GEN9_SKIP_DOTNET=1`
- `GEN9_SKIP_GHIDRA=1`
- `GEN9_SKIP_PKNX=1`
- `GEN9_SKIP_EMULATOR=1`

Example:

```bash
GEN9_SKIP_SYSTEM=1 bash tools/bootstrap_gen9_linux.sh
```

## Local layout

```text
.local-tools/
├── dotnet/
├── ghidra/
├── venv/
├── src/
│   ├── pkNX/
│   └── Ryubing/
├── ryubing-build/
└── env.sh
```

All of `.local-tools/` is disposable and reproducible from the bootstrap and lock manifest.
