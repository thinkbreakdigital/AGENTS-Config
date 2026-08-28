---
name: pixel-art-codex
description: Use the installed Pixel Art Codex pipeline to design, render, export, validate, or inspect deterministic pixel-art sprites, animations, tiles, props, effects, palettes, sprite sheets, GIF/APNG-ready assets, and game-art deliverables from any consuming repository. Trigger for new or revised pixel assets, reference-driven sprite work, procedural Pillow generators, asset animation, export bundles, or Pixelorama inspection.
---

# Pixel Art Codex

Use the shared pipeline while keeping asset-specific inputs, code, and outputs in the consuming
project. The conventional workspace is `./pixel-art`; the pipeline repository is tooling only.

## Establish context

1. Read the consuming repository's `AGENTS.md` files and `/spec` before meaningful changes. Its
   product requirements and asset paths take precedence.
2. Run `pixel-art-codex guide` from the consuming repository root.
3. Read the pipeline `AGENTS.md` path printed by `guide`, plus the linked art/workspace docs needed
   for the task.
4. Record `git status --short` for both the consumer and pipeline repositories. Preserve unrelated
   changes.
5. Inspect existing consumer components, asset conventions, references, palettes, specifications,
   generators, and tests before creating anything.

If `pixel-art-codex` is unavailable, report that clearly and direct the user to run `make install`
in their Pixel Art Codex checkout. Do not invent a fallback pipeline.

## Build an asset

1. Run `pixel-art-codex init-workspace`. This creates the default `$PWD/pixel-art` directories and
   no sample art. Pass `--workspace /absolute/path` only when the consumer requires another path.
2. Put authoritative visual inputs in `pixel-art/references/<asset_name>/`. Record any interpretation
   that is not visually unambiguous.
3. Choose one lowercase safe asset name. Keep it identical across reference folders, specification,
   generator, tests, frames, sheets, metadata, and downstream game references.
4. Define named `#RRGGBBAA` colors in `pixel-art/palettes/<palette_name>.json`. Use only declared
   colors and binary alpha.
5. Define canvas, frame count/timing, palette path, anchor, layers, animation tags, scale,
   background, and optional seed in `pixel-art/specifications/<asset_name>.json`.
6. Implement `pixel-art/generators/<asset_name>.py` with
   `render(specification, palette) -> Sequence[Image.Image]`. Use integer coordinates, Pillow RGBA,
   pipeline primitives/layers/animation helpers, nearest-neighbor scaling, stable ordering, and
   local seeded randomness only. Never use antialiasing, subpixels, global randomness, external
   image generation, or AI image APIs.
7. Add reference- and asset-specific checks in `pixel-art/tests/test_<asset_name>.py` when the
   design has invariants beyond generic validation.
8. Run:

   ```bash
   pixel-art-codex build-asset \
     --spec ./pixel-art/specifications/<asset_name>.json
   ```

   This renders twice, compares exact bytes, validates, and writes the complete bundle to
   `./pixel-art/exports/<asset_name>/`. Use `--output /absolute/path` when explicitly required.
9. Run the consumer's relevant tests and any external generator tests. Inspect native-size and
   nearest-neighbor previews against the same reference set.

Use `render`, `export`, and `validate-assets` separately only when stage-level diagnosis or custom
path control is useful. Run `pixel-art-codex --help` for exact options.

## Preserve reference consistency

Before finishing, compare asset identifiers, dimensions, frame indexes, timing, loop behavior,
tags, anchors, facing direction, layers, palette names/values, scale, background, seed, filenames,
sheet rectangles, metadata, and downstream consumer paths. When a canonical value changes, search
the whole workspace and consumer integration for the old value and update every dependency in the
same task. Do not silently mix reference revisions or invent occluded details.

## Isolation and delivery

- Never write asset-specific files to the pipeline repository.
- Consumer files belong under its selected workspace or explicit export path. They may appear in
  consumer Git status; that is expected and subject to the consumer's own tracking policy.
- The tool does not stage, commit, push, publish, or create releases. Do none of those unless the
  user explicitly requests them.
- Do not open Pixelorama or another GUI during unattended work. When manual inspection is requested,
  use the pipeline's documented `scripts/open_in_pixelorama.sh` with an existing exported file.
- Finish by verifying that pipeline Git status matches its initial state, consumer changes are
  confined to intended paths, deterministic checks pass, and no stale references remain.
