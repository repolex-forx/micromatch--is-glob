# Repolex Knowledge Graph of micromatch/is-glob

RDF knowledge graph data for [micromatch/is-glob](https://github.com/micromatch/is-glob), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download micromatch/is-glob
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 627ca7e552c69e8d62d620b4715a2658267b3d17
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 627ca7e552c69e8d62d620b4715a2658267b3d17.nq.gz
│   └── repolex
│       └── 627ca7e552c69e8d62d620b4715a2658267b3d17
│           └── chunk-001.nq.gz
├── blob
│   ├── 3f2eca18f1bc0f3117748e2cea9251e5182db2f7.nq.gz
│   ├── 4a3f1d3d78147c9ed97e89858bd21353681f75ae.nq.gz
│   ├── 53e9cb6093482098737b00790c9263097b28ae51.nq.gz
│   ├── 620f563eccf081ce0d2db2dda5c9989baf778183.nq.gz
│   ├── 740724b276e289aec14ee6ce99d42ab9a6eb4b48.nq.gz
│   ├── 7e8c9d19ede190e811abcbcc4fe0efb8f72e8c52.nq.gz
│   ├── 818e0724ac1f6a03159d26ec6825a534a8bdb48a.nq.gz
│   ├── 858af0378e9d36813353b51271aec88ee0d3328b.nq.gz
│   ├── 96eeb8ed83fe814971c4d6a8ced936660a258972.nq.gz
│   ├── ca944adafe5bb051e46d82fc2dd481b51aaaf2c1.nq.gz
│   ├── cc697457be5b8870427b49849625a6b6934350f2.nq.gz
│   ├── ccfe581f7b025eb51eff3989fefa85f3fe6b9293.nq.gz
│   └── f2a4ab2cdb91eaafb89d16ea203b0aedf4d31e51.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 627ca7e552c69e8d62d620b4715a2658267b3d17.nq.gz
├── filetree
│   └── 627ca7e552c69e8d62d620b4715a2658267b3d17.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 23 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |

## Source repository

[micromatch/is-glob](https://github.com/micromatch/is-glob)

---
*Parsed on 2026-09-15 by [repolex](https://repolex.ai)*
