# VaneDB

**Embeddable vector database for edge AI.** SIMD similarity search for
Rust, Python, C, and WebAssembly.

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

**0.2.0** is published. Install the Rust crate, the Python package, or the
WebAssembly package:

```sh
cargo add vanedb
python -m pip install vanedb
npm install @vanedb/wasm
```

> The former `vanedb-cpp` and `vanedb-bench` repositories were
> consolidated into this one and are archived.

## Highlights

- **One crate, few dependencies** — a single Rust crate plus thin bindings
- **SIMD-optimized** — ARM NEON and x86 AVX2, with a scalar reference path
- **Multiple indexes** — brute-force, HNSW, and memory-mapped
- **GPU** — experimental Metal distance scans on macOS; they accelerate no index. CUDA is not implemented
- **Cross-platform** — Linux, macOS, Windows, iOS, Android, WASM

Measured numbers, including the cross-engine comparison, live in
[`bench/`](https://github.com/vanedb/vanedb/tree/main/bench#readme) rather than
here, so they stay next to the harness that produced them.

---

Maintained by [@tsvet01](https://github.com/tsvet01). MIT-licensed.
