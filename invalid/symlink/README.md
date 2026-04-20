---
public: false
---

# Symlink skip scenario

Holds a tracked git symlink (`link-to-real.png`, mode `120000`).
`frontmatter-filter` emits a `Skipping tracked symlink: ...` warning for
every symlink in the source tree, whether or not anything references it.
