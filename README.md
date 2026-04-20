# Obsidian Test Vault

This fixture simulates a medium-sized Obsidian vault for integration testing.

## Layout

- Everything outside `invalid/` is "valid" vault content — shapes and patterns
  a real user could plausibly author. Broken or private references inside
  that tree are there because users make mistakes, not because the content
  itself is malformed.
- Everything under `invalid/` is **deliberately malformed**: tracked symlinks
  (mode `120000`), markdown files with unparseable YAML, etc. They exist
  only to exercise `frontmatter-filter` fail-safes. See `invalid/README.md`.

Downstream consumers reusing this vault as a generic Obsidian fixture can
exclude `invalid/` cleanly. The `invalid/` root is `public: false`, so its
contents never reach the mirror output by default.

## Intentional coverage (non-exhaustive)

- attachments referenced from root, nested, and sibling paths
- duplicate attachment basenames to exercise Obsidian-style embed ambiguity
- a tracked symlink that should be skipped by `frontmatter-filter`
  (`invalid/symlink/`)
- unparseable YAML frontmatter that must not abort parsing
  (`invalid/malformed-yaml/`)
