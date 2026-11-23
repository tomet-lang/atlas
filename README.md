<!-- Generated from .tomet/readme.tmt. Edit that, then `tomet export .`. -->

# Atlas

The canonical knowledge map, shared dictionaries, repository relationships, and cross-repository guides for the Tomet ecosystem.

## Overview

`atlas` serves as the upstream Zettelkasten knowledge base for the Tomet ecosystem.
While each tool repository owns its own specification and implementation-derived artifacts, and `bearings` manages fluid development plans and roadmaps, `atlas` holds settled, cross-cutting knowledge under strict verification (no `@draft` markers, no broken links).

## Layout

- `dict/` -- Shared Tomet dictionaries (starting with `tomet.dict.tmt`).
- `docs/` -- Cross-repository concepts and user-facing ecosystem guides (such as `docs/overview.tmt`).
- `repos/` -- Canonical descriptions of repositories and their relationships across the ecosystem.

## Using Atlas

### Taking a dictionary with `catasto.upstream`

Declare `atlas` in `catasto.ctmt` and pull the shared dictionary file, then run `catasto sync`:

```text
::kind(catasto, version: "1.0.0")
::upstream(
  atlas: catasto.git("https://github.com/tomet-lang/atlas.git", rev: main)
)

"tmtroot/dict/tomet.dict.tmt": catasto.upstream(
  atlas,
  path: "dict/tomet.dict.tmt"
)
```

### Mounting Atlas as a repository with `catasto.repo`

Portals such as `website` can mount the full `atlas` worktree into `repos/atlas`:

```text
"repos/atlas": catasto.repo(
  "https://github.com/tomet-lang/atlas.git",
  branch: main,
  submodule: false
)
```

## License

Dual-licensed under the MIT license and the Apache License 2.0, at your option.

