# Repolex Knowledge Graph of scikit-image/skimage-org

RDF knowledge graph data for [scikit-image/skimage-org](https://github.com/scikit-image/skimage-org), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download scikit-image/skimage-org
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fc1307b3c6b8f922d27ba468fee45f25bdac3248
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fc1307b3c6b8f922d27ba468fee45f25bdac3248
│           └── chunk-001.nq.gz
├── blob
│   ├── 99fe2896ecd6ca9c56d3afffeb3217c217bf38f3.nq.gz
│   ├── aa15ef8aa3d6e0d53cc2d52a31d6347cbe6847a4.nq.gz
│   └── da4f09504cd7f52ed9eefe8bbf2fdb420225145a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fc1307b3c6b8f922d27ba468fee45f25bdac3248.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 9 files
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
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[scikit-image/skimage-org](https://github.com/scikit-image/skimage-org)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
