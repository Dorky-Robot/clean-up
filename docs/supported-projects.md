# Supported Projects

clean-up detects project types by looking for marker files in the target directory.

## Rust

**Marker:** `Cargo.toml`

| Directory | Description |
|---|---|
| `target/` | Compiled artifacts and dependencies |

## Node.js

**Marker:** `package.json`

| Directory | Description |
|---|---|
| `node_modules/` | Installed dependencies |
| `.next/` | Next.js build cache |
| `dist/` | Build output |
| `.turbo/` | Turborepo cache |
| `.parcel-cache/` | Parcel bundler cache |

## Python

**Marker:** `pyproject.toml`, `setup.py`, or `requirements.txt`

| Directory | Description |
|---|---|
| `.venv/` | Virtual environment |
| `venv/` | Virtual environment (alternate name) |
| `__pycache__/` | Bytecode cache |
| `.mypy_cache/` | mypy type checker cache |
| `.pytest_cache/` | pytest cache |
| `.ruff_cache/` | Ruff linter cache |

## Elixir

**Marker:** `mix.exs`

| Directory | Description |
|---|---|
| `_build/` | Compiled artifacts |
| `deps/` | Fetched dependencies |

## Go

**Marker:** `go.mod`

| Directory | Description |
|---|---|
| `vendor/` | Vendored dependencies |

## Swift / Xcode

**Marker:** `*.xcodeproj`, `*.xcworkspace`, or `Package.swift`

| Directory | Description |
|---|---|
| `.build/` | Swift Package Manager build artifacts |
| `DerivedData/` | Xcode build cache |
| `Pods/` | CocoaPods dependencies |

## Flutter / Dart

**Marker:** `pubspec.yaml`

| Directory | Description |
|---|---|
| `.dart_tool/` | Dart tool cache |
| `build/` | Build output |
