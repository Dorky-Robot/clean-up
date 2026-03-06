# Usage

## Install

=== "Homebrew (recommended)"

    ```bash
    brew install dorky-robot/tap/clean-up
    ```

=== "Manual"

    ```bash
    curl -o /usr/local/bin/clean-up https://raw.githubusercontent.com/Dorky-Robot/clean-up/main/bin/clean-up
    chmod +x /usr/local/bin/clean-up
    ```

## Commands

### Direct clean

Clean one or more project directories:

```bash
clean-up ~/Projects/my-app
clean-up ~/Projects/app1 ~/Projects/app2 ~/Projects/app3
```

If the directory has a recognized project marker (e.g. `Cargo.toml`, `package.json`), clean-up detects the type and asks about each cleanable directory:

```
Scanning /Users/you/Projects/my-app ...
  == Rust project ==
  Delete target/ (13G)? [y/N] y
    Deleted target/ (13G)
```

### Interactive browse

List all subdirectories of a parent folder, see what's reclaimable, and pick which to clean:

```bash
clean-up ls ~/Projects
```

Output:

```
  #    Directory                      Last modified  Reclaimable
  ---  ------------------------------ -------------- -----------
  1    old-experiment                 Oct 20 2024    17M
  2    my-rust-app                    Jan 15 2025    25.4G
  3    web-frontend                   Mar 06 2026    431M

Enter numbers to clean (e.g. 1 3 5), 'a' for all, or 'q' to quit:
>
```

- Enter space or comma-separated numbers: `1 3` or `1, 3`
- Enter `a` to clean all listed projects
- Enter `q` to quit

### Monorepo / workspace support

If no project marker is found at the top level, clean-up automatically scans subdirectories:

```bash
clean-up ~/Projects/my-monorepo
```

```
Scanning /Users/you/Projects/my-monorepo ...
  No project file found. Scanning subdirectories...

--- backend ---
  == Rust project ==
  Delete target/ (8.2G)? [y/N]

--- frontend ---
  == Node.js project ==
  Delete node_modules/ (450M)? [y/N]
```

### Version

```bash
clean-up -v
clean-up --version
```
