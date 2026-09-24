# VaneDB

**Embeddable vector database for edge AI.** SIMD-optimized similarity search
for native applications and WebAssembly. Bring your own embeddings; VaneDB
stores and searches vectors in-process.

## One repository

Everything lives in **[vanedb](https://github.com/vanedb/vanedb)**.

| Component | What it is |
|---|---|
| `vanedb/` | The Rust engine — the one that ships |
| `vanedb-py/` · `vanedb-wasm/` · `vanedb-capi/` | Python (PyO3), WASM, and C ABI bindings |
| `cpp/` | A header-only C++ engine, frozen as reference code |
| `bench/` · `conformance/` | Cross-engine benchmarks and shared fixtures |

The Rust engine is what receives features and releases. The C++ engine is not
a second product: it stays as the other arm of the cross-engine benchmark and
as a drop-in header for existing C++ projects, and features are not ported to
it.

## Install

The Rust engine is published on [crates.io](https://crates.io/crates/vanedb)
and [PyPI](https://pypi.org/project/vanedb/):

```sh
cargo add vanedb
python -m pip install vanedb
```

See [Getting started](https://github.com/vanedb/vanedb/blob/main/docs/GETTING_STARTED.md)
for examples and the [WebAssembly guide](https://github.com/vanedb/vanedb/blob/main/vanedb-wasm/README.md)
for JavaScript. The supplementary `vanedb-cpp` Python package is not published.
The former `vanedb-cpp` and `vanedb-bench` repositories were consolidated into
the monorepo and are archived.

## Highlights

- **One crate, few dependencies** — a single Rust crate plus thin bindings
- **SIMD-optimized** — ARM NEON and x86 AVX2, with a scalar reference path
- **Multiple indexes** — brute-force, HNSW, and memory-mapped
- **Platform evidence** — native and WebAssembly tests, with iOS simulator and
  Android emulator acceptance; see the [platform support policy](https://github.com/vanedb/vanedb/blob/main/docs/PLATFORMS.md)
  for exact targets, deployment floors, and support tiers

The optional macOS `gpu-metal` feature is experimental: it exposes a standalone
compute API, and no index uses it for acceleration. CUDA is not implemented.

Measured numbers, including the cross-engine comparison, live in
[`bench/`](https://github.com/vanedb/vanedb/tree/main/bench#readme) rather than
here, so they stay next to the harness that produced them.

---

Maintained by [@tsvet01](https://github.com/tsvet01). MIT-licensed.
