# VaneDB

**Embeddable vector database for edge AI.** SIMD-optimized similarity search
that runs anywhere — from mobile devices to GPUs.

## Implementations

| Repo | Language | When to use |
|---|---|---|
| **[vanedb](https://github.com/vanedb/vanedb)** | Rust | `cargo add vanedb`, Python (PyO3), WASM bindings |
| **[vanedb-cpp](https://github.com/vanedb/vanedb-cpp)** | C++20 header-only | Drop into any CMake/Bazel project, no toolchain needed |

Features generally land in Rust first; core algorithms and persistence formats
are synced to C++. Both are MIT-licensed.

## Highlights

- **Header-only / single crate** — minimal dependencies
- **SIMD-optimized** — ARM NEON and x86 AVX2, ~100ns L2 distance (768d)
- **Multiple indexes** — brute-force, HNSW, memory-mapped
- **GPU acceleration** — Metal (Apple Silicon); CUDA is experimental
- **Cross-platform** — Linux, macOS, Windows, iOS, Android, WASM

---

Maintained by [@tsvet01](https://github.com/tsvet01).