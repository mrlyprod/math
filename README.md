mrly-math; a MrlyMath crate: the designs, codes, cells, cubes and hexagons, their counts, graphs and names, digit designs on the line, and wheels

# MATH

- One repo, one crate, one version, on `mrly-core` and `mrly-num`; `js/`, `py/` and `cli/` are its bindings, written by `mrly-bridge`: `@mrlyprod/math` (npm), `mrly.math` (PyPI `mrly-math`) and the `mrly-math` command.
- The hand-written crossings of codes and cells live in `src/hand/` behind the cargo features `js` and `py`, over `mrly-core`'s; a leaf that sees math takes `mrly-math = { version, features = ["js"] }`.
- `scripts/bridge.sh` regenerates the leaves from `bridge.toml` and the sources; `scripts/bridge.sh check` says what is stale.
- `scripts/check.sh` is the one gate: fmt, clippy, test, doc, bridge check, ruff, wasm, the leaves' tests, leak.
- A fresh clone runs `scripts/wasm.sh` once before any host builds: it writes `js/pkg/`, which is not committed.
- Until the crates are published, clone the fleet beside this repo: `scripts/bridge.sh` runs the sibling `../bridge`, and a `.cargo/config.toml` with `[patch.crates-io]` rows points every `mrly-*` dependency at its sibling folder.
- Every file `.gitattributes` marks `linguist-generated` is the bridge's; never hand-edit one.
- Docs: [docs.rs/mrly-math](https://docs.rs/mrly-math).
