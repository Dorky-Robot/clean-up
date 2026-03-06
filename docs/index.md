# clean-up

**Interactive CLI to reclaim disk space from project build artifacts and caches.**

---

Point it at a directory, it detects the project type, shows you what's taking up space, and asks before deleting anything.

## Quick start

```bash
brew install dorky-robot/tap/clean-up
```

```bash
# Browse projects, see reclaimable space, pick which to clean
clean-up ls ~/Projects

# Clean specific projects
clean-up ~/Projects/my-app ~/Projects/another-app

# Clean current directory
clean-up
```

## Interactive mode

`clean-up ls` lists subdirectories sorted oldest-first, with reclaimable space:

```
  #    Directory                      Last modified  Reclaimable
  ---  ------------------------------ -------------- -----------
  1    old-experiment                 Oct 20 2024    17M
  2    my-rust-app                    Mar 06 2026    25.4G
  3    web-frontend                   Mar 06 2026    431M

Enter numbers to clean (e.g. 1 3 5), 'a' for all, or 'q' to quit:
> 1, 2
```

Each item is confirmed individually — nothing is deleted without your say-so.

---

[Usage →](usage.md){ .md-button .md-button--primary }
[Supported Projects →](supported-projects.md){ .md-button }
