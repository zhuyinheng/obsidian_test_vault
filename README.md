# Obsidian Test Vault

This fixture simulates a medium-sized Obsidian vault for integration testing.

It intentionally includes:

- attachments referenced from root, nested, and sibling paths
- duplicate attachment basenames to exercise Obsidian-style embed ambiguity
- a tracked symlink that should be skipped by `frontmatter-filter`
