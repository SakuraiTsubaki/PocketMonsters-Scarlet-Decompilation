# Technical Source Map

This document maps high-value public technical sources for Pokémon Scarlet. It is a public-source reconstruction aid, not a substitute for direct target-build observation.

## Evidence boundary

The project currently has no local retail ROM/game dump. Findings below are derived from public source code, documentation, datamines, and reverse-engineering tools. They remain public-source evidence unless independently reproduced against a verified target later.

## Save-data structure — PKHeX

Canonical source: `kwsch/PKHeX`.

`PKHeX.Core/Saves/Access/SaveBlockAccessor9SV.cs` exposes a dedicated `SAV9SV` block accessor. Public source currently identifies, among many others:

- box and party data
- items, trainer status, play time, Pokédex and configuration
- player fashion and appearance
- Paldea, Kitakami and Blueberry raid spawn lists
- seven-star raid capture/defeat history
- Blueberry Quest records and Club Room data
- money, League Points and Blueberry Points
- hidden-item status blocks for Paldea, Area Zero and Kitakami
- Mystery Gift and DLC gift blocks
- sandwich records
- field items and defeated-trainer history
- BCAT Tera Raid fixed rewards, lottery rewards, enemy data, priority data and version identifier
- BCAT mass-outbreak zones for Paldea, Kitakami and Blueberry plus outbreak Pokémon data
- player coordinates, rotation, field ID and current location ID
- fashion unlock blocks, profile pictures and trainer icons

Important revision evidence in the public source includes the seven-star raid defeat-history split introduced after 2.0.1 and an expanded defeated-trainer history block noted for 2.0.2+.

Do not treat block names, offsets or behavior as project `Observed` until verified against an identified target build.

## Tera Raid / Mass Outbreak research lineage

### Tera Finder — `Manu098vm/Tera-Finder`

PKHeX.Core-based Scarlet/Violet tool supporting:

- raid viewing/editing
- mass-outbreak viewing/editing
- Poké Portal News raid/outbreak import
- raid and reward seed calculations
- raid legality seed reversal
- seven-star/progress/caught flag editing
- remote-device access

Its credits provide an important research lineage linking PKHeX, pkNX, SysBot.NET, RaidCrawler, sv-live-map, item-reward research, event group-ID research and disassembled-game pointer work.

### RaidCrawler — `LegoFigure11/RaidCrawler`

Public Scarlet/Violet sys-botbase raid viewer. It is an upstream source for RAM access, raid reward structures, search logic, coordinates and map display work subsequently reused by other tools.

### Event Raid Injector — `Insektaure/Event-Raid-Injector`

Public tool targeting Scarlet/Violet 4.0.0 that preserves/imports historical Poké Portal raid-event and mass-outbreak data into saves. It is valuable for reconstructing event save/BCAT structures and seven-star capture flags. Event data must still be cross-checked against official schedules and independent archives.

### pkTeraRaid / sv-live-map

These projects provide additional raid map coordinates, Paldea/Kitakami/Blueberry map presentation and save/RAM handling leads. Coordinate provenance must be tracked because several downstream tools share upstream dumps.

## FlatBuffers and resource metadata — PokeDocs

Canonical source: `pkZukan/PokeDocs`.

The dedicated `SV/` tree currently contains `Flatbuffers/` and `Hashlists/`. The FlatBuffers tree is split into at least:

- `animation/`
- `customization/`
- `field/`
- `filesystem/`
- `model/`
- `pml/`
- `render/`
- `resources/`
- `scene/`

This makes PokeDocs a primary public technical index for reconstructing Trinity/FlatBuffer schemas and hashed resource identifiers. Each subtree must be enumerated file-by-file in later format sweeps rather than treating the directory as one source.

## Trinity/container/tooling lineage

- `pkZukan/gftool` — TRPFS/TRPFD, Trinity serializers, file/model/scene tooling.
- `ChicoEevee/Pokemon-Switch-Model-Importer-Blender` — model/animation import pipeline and Trinity-related model formats.
- `ChicoEevee/PokeModding-PLA-SV-Blender` — Blender exporters and PokeDocs schema usage.
- `AncientDbri/Pokemon-Switch-Model-Importer-Plus` — derivative extended importer/exporter; track separately from upstream only where materially divergent.
- `KillzXGaming/Switch-Toolbox` — historical Switch resource inspection support; archived, but useful for format lineage.

## Text and structured game data

- `Pokemon-Project-com/sv-text` — multilingual common/script text, including Japanese kana/kanji, Korean, English, Chinese and European languages.
- `kwsch/pkNX` — parsers/dumpers used by multiple downstream legality and raid projects.
- `KotMatrosk1n/KM-Editor` — public game-specific data models for Pokémon, moves, items, trainers, encounters, gifts/trades, raids, shops, placement, models and audio.
- `svfeplvce/ProjectSky` — personal/evolution/learnset/trainer editing lineage; numerous forks exist and must be deduplicated unless materially divergent.

## Next technical enumeration targets

Status remains **Sweeping**.

- enumerate every file under `PokeDocs/SV/Flatbuffers` and `SV/Hashlists`
- inventory PKHeX Gen9/SV save substructures and revision-specific block changes
- trace Tera Finder → RaidCrawler → sv-live-map → pkNX/PKHeX provenance for shared coordinates/reward/event data
- enumerate Poké Portal/BCAT raid and outbreak table structures and historical event archives
- enumerate model, animation, texture, shader, audio and placement formats
- map source/tool support by Scarlet/Violet revision rather than assuming latest-only compatibility
