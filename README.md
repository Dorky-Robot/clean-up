# clean-up

[![Discord](https://img.shields.io/discord/1483879594619568291?color=5865F2&label=Discord&logo=discord&logoColor=white)](https://dorkyrobot.com/discord)

Interactive CLI to reclaim disk space from project build artifacts, caches, and dependencies.

Detects project type automatically and asks before deleting anything.

## Install

```
brew install dorky-robot/tap/clean-up
```

## Usage

```bash
# Clean a specific project
clean-up ~/Projects/my-rust-app

# Clean multiple projects at once
clean-up ~/Projects/app1 ~/Projects/app2

# Browse projects interactively — lists subdirectories sorted by oldest first,
# shows reclaimable space, and lets you pick which ones to clean
clean-up ls ~/Projects

# Clean current directory
clean-up
```

### Interactive mode

`clean-up ls` shows a table of projects with reclaimable space:

```
  #    Directory                      Last modified  Reclaimable
  ---  ------------------------------ -------------- -----------
  1    old-experiment                 Oct 20 2024    17M
  2    my-rust-app                    Mar 06 2026    25.4G
  3    web-frontend                   Mar 06 2026    431M

Enter numbers to clean (e.g. 1 3 5), 'a' for all, or 'q' to quit:
> 1, 2
```

### What it detects

| Project type | Marker file | Cleaned directories |
|---|---|---|
| Rust | `Cargo.toml` | `target/` |
| Node.js | `package.json` | `node_modules/`, `.next/`, `dist/`, `.turbo/`, `.parcel-cache/` |
| Python | `pyproject.toml`, `setup.py`, `requirements.txt` | `.venv/`, `venv/`, `__pycache__/`, `.mypy_cache/`, `.pytest_cache/`, `.ruff_cache/` |
| Elixir | `mix.exs` | `_build/`, `deps/` |
| Go | `go.mod` | `vendor/` |
| Swift/Xcode | `*.xcodeproj`, `Package.swift` | `.build/`, `DerivedData/`, `Pods/` |
| Flutter/Dart | `pubspec.yaml` | `.dart_tool/`, `build/` |

If no project marker is found at the top level, it scans subdirectories automatically (useful for monorepos and workspace directories).

## License

Licensed under either of:

- Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE))
- MIT license ([LICENSE-MIT](LICENSE-MIT))

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally
submitted for inclusion in the work by you, as defined in the Apache-2.0
license, shall be dual licensed as above, without any additional terms or
conditions.
