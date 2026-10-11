# Repolex Knowledge Graph of agronholm/redio

RDF knowledge graph data for [agronholm/redio](https://github.com/agronholm/redio), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/redio
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6f3eab2071c5f0d1915f6c6bfc5c468e3c29933c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6f3eab2071c5f0d1915f6c6bfc5c468e3c29933c
│           └── chunk-001.nq.gz
├── blob
│   ├── 3d2fbbfb0ee4c4e445ed3da3e7870651b6f61dac.nq.gz
│   ├── 42d6e3c9b7272cd2e64bb1310c1a555c27993ccc.nq.gz
│   ├── 45f838db1f49bbb57a3f541c9582bc86ea1a0c97.nq.gz
│   ├── 568731953544440525e504e1116092640125990b.nq.gz
│   ├── 59e8edf8129db05fa695355b16fa338f44ab3903.nq.gz
│   ├── 5f4a13a225db317dbb3f4cb3ca1e5dc5b10eec2a.nq.gz
│   ├── 71e28bab1a52e90cf9e087cf021ce9aeb0cc8da2.nq.gz
│   ├── 7e23b476604c3262a7d03ef786f2ee35c38b04cd.nq.gz
│   ├── 7ef978cd686dfe74d31d64041765154d55cce559.nq.gz
│   ├── 81dc3fd3ee0b9dc7c510e3f310d0b0f48c91ded2.nq.gz
│   ├── 9b7f56b8f79c876b2eb8632b9f5f8ba5c41a7bb3.nq.gz
│   ├── a895fcd4716b45d72486b296f3e71e5f16bf92f4.nq.gz
│   ├── a8e6db5716303cf086538cf9e5147af96512dfdb.nq.gz
│   ├── ac7abfd996433837f2069eb73ba35dc62161bb8a.nq.gz
│   ├── bb5902dbe7c80bc34c5eb5ad5731abaa1569296f.nq.gz
│   ├── e03b736ffda76dc1cfcb0b353f85d9ea347eae36.nq.gz
│   └── e7e9c734ead5a9b397fa3243cad0e0ff5fc7694b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6f3eab2071c5f0d1915f6c6bfc5c468e3c29933c.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 23 files
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

[agronholm/redio](https://github.com/agronholm/redio)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
