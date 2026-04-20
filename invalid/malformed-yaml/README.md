---
public: false
---

# Malformed YAML scenario

`broken-yaml.md` contains a frontmatter block whose YAML does not parse.
The tool must emit a `Failed to parse YAML frontmatter: ...` warning and
treat `public` as unset (so the file is not published).
