# Repolex Knowledge Graph of pydantic/demo-endpoints

RDF knowledge graph data for [pydantic/demo-endpoints](https://github.com/pydantic/demo-endpoints), parsed by [repolex](https://repolex.ai).

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
rlex download pydantic/demo-endpoints
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ff1f698deecdf6b3bbdb9e0b994753615fb03c48
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ff1f698deecdf6b3bbdb9e0b994753615fb03c48
│           └── chunk-001.nq.gz
├── blob
│   ├── 2276dd58b2c051579a0059d144cff3cad9da33b3.nq.gz
│   ├── 244894dd16cb9d3f99c619a10ebdd1df1cd60e18.nq.gz
│   ├── 5c2d8056ca0acfa7e04e9c0638b621b6de3e0c92.nq.gz
│   ├── 6e6c941da68a6232a3c3ab05b6beeda10501e9c8.nq.gz
│   ├── a4c05c4f5369d3332cd195660f5f57fc40a8e50a.nq.gz
│   ├── b507b5cb60bc09a9788c309c187acc1d4e28e45d.nq.gz
│   ├── cf93181f8489140b420080f7233ada601161fc99.nq.gz
│   ├── defb5b6acd93ce3ceaee05372a071fd3e26ef32e.nq.gz
│   ├── edac8a05c831c14c4a4f96a5f59c320e76da5643.nq.gz
│   └── f326a58539328611a4f62cd72b1f1d29f6f3ad77.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ff1f698deecdf6b3bbdb9e0b994753615fb03c48.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 16 files
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

[pydantic/demo-endpoints](https://github.com/pydantic/demo-endpoints)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
