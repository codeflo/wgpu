# wgpu "minimal"

This is an unmaintained fork of the [WGPU](https://github.com/gfx-rs/wgpu) project that aims to reduce the compiled binary size by removing removing some API options, and targeting modern GPUs only.

WGPU itself is an implementation of [WebGPU](https://www.w3.org/community/gpu/) API in Rust, targeting both native and the Web.

**This fork not intended for general use.** It's barely tested and might only work with a specific project setup. It does, however, reduce the binary size in one program from ~7MB to ~1.5MB.

## Changes compared to the official WGPU

- Only support the most modern graphics backend for each platform:

  - Windows: Vulkan
  - Unix: Vulkan
  - macOS/iOS: Metal
  - WASM: WebGL

- Only support the WGSL input format for shaders

## Adding WGPU minimal to a project

```toml
# Cargo.toml

[dependencies]
wgpu = "0.12"

[patch.crates-io]
wgpu = { git = "https://github.com/codeflo/wgpu" }
wgpu-core = { git = "https://github.com/codeflo/wgpu" }
wgpu-hal = { git = "https://github.com/codeflo/wgpu" }
wgpu-types = { git = "https://github.com/codeflo/wgpu" }
```
