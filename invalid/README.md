---
public: false
---

# Intentionally Invalid Fixtures

Files under `invalid/` are deliberately malformed to exercise
`frontmatter-filter` fail-safes:

- `invalid/symlink/` — a tracked git symlink (mode `120000`) that must be
  skipped with a warning.
- `invalid/malformed-yaml/` — a markdown file whose YAML frontmatter does not
  parse; the tool must continue with a warning and treat `public` as unset.

Downstream consumers reusing this vault as a "realistic Obsidian vault"
should exclude the `invalid/` tree. The root is `public: false`, so nothing
under `invalid/` reaches the publish output by default.
