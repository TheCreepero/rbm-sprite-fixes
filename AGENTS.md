# RBM Sprite Fixes - Agent Rules

Shared rules for every mod in this tree (file encodings, build commands, engine knowledge, git) are in the Modding Manager's `../../AGENTS.md`. `CLAUDE.md` and `GEMINI.md` import this file.

## What this mod is
- Restores the sub-unit sprites that RBM's GFX Overhaul drops from interface/subuniticons.gfx.
- Standard single-root layout: `descriptor.mod`, `build.ps1`, content folders, `tests/`, `tools/`, `wiki/` at the root; `artifacts/` and `scratch/` are git-ignored.

## Mod invariants
- RBM's `interface/subuniticons.gfx` replaces vanilla's whole [LOAD-010] and lacks 31 of its sprites [RBM-008]; `interface/rbm_sprite_fixes_subuniticons.gfx` declares them again, copied verbatim from vanilla, under a file name of its own so it adds to RBM's file instead of replacing it.
- Never ship a file under a vanilla or RBM file name. Load after RBM (`dependencies` in `descriptor.mod`).
- After an RBM or game update, compare the sprite names again (RBM-008 says how) and drop any sprite RBM declares itself again.

## Commands beyond build.ps1
- None yet.

## Read when
| Task | Read |
|---|---|
| Publishing to the Workshop | `WORKSHOP_DESCRIPTION_GUIDELINES.md` |

## Engine Knowledge
- Engine facts live in the Modding Manager's register, reached through the user-level `hoi4-modding-knowledge` skill: search it before a new kind of file and before asking for a game launch, cite ids here, never write a fact into this repository.
- Topics this mod leans on: `encoding-and-syntax`, `loading-and-overrides`.
- `tests/Knowledge.Tests.ps1` runs the register's audit for this repository; it is a copy the Manager keeps current.