# Agent Guidelines for CozyReq

## Build & Test Commands
- **Dev**: `mise run dev:app` (runs Tauri app) or `npm run dev` (Vite only)
- **Build**: `npm run build` (frontend), `cargo build` (Rust)
- **Test**: `cargo test` (all Rust tests), `cargo test test_name` (single test)
- **Lint**: `cargo clippy -- -D warnings` (Rust), `cargo fmt -- --check` (format check)
- **Format**: `cargo fmt` (Rust auto-format)

## Code Style

### TypeScript/SolidJS
- Use **SolidJS** primitives (`createSignal`, `createEffect`, etc.)
- **Strict mode** enabled: all types required, no implicit any
- Import order: external deps, Tauri API, local modules, CSS/assets
- Use `invoke()` from `@tauri-apps/api/core` for Rust backend calls
- JSX: preserve mode with `jsxImportSource: "solid-js"`

### Rust
- **Edition 2024**, strict Rust 2021+ idioms
- Use `#[tauri::command]` for exposed functions
- Format with `rustfmt`, lint with `clippy` (zero warnings policy)
- Error handling: use `Result<T, E>` and `.expect()` with descriptive messages
- Naming: snake_case for functions/vars, PascalCase for types
