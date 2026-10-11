# Repolex Knowledge Graph of pallets/werkzeug-website

RDF knowledge graph data for [pallets/werkzeug-website](https://github.com/pallets/werkzeug-website), parsed by [repolex](https://repolex.ai).

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
rlex download pallets/werkzeug-website
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a1243ec5104a0b5eb51d74f40c8ff2386074b101
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a1243ec5104a0b5eb51d74f40c8ff2386074b101
│           └── chunk-001.nq.gz
├── blob
│   ├── 10e98d4f08b5e76d1603b3f7bc85664a820c4c68.nq.gz
│   ├── 4183c1b57b46c58c2feebba47f8803babd762311.nq.gz
│   ├── 4c83f83a2dfbc6bd1bb90dea4ec757b4bc2ce993.nq.gz
│   ├── 6878989fe8da068f4a9c73d389c309b8c4c1568c.nq.gz
│   ├── 9cedb0614a658347219e072fbdb19e28c1da72cf.nq.gz
│   ├── b2f4cb3ce6d7f6315ac9070d754d8a08d5d4074a.nq.gz
│   ├── c4272d078b6a80f91119bd3834e926cd56d35c38.nq.gz
│   ├── dd9a618779dce35368431e5b751adb88a669e898.nq.gz
│   ├── e35d8850c9688b1ce82711694692cc574a799396.nq.gz
│   └── f9056e736813af7280377cfde5c88c1c86b82587.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a1243ec5104a0b5eb51d74f40c8ff2386074b101.nq.gz
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

[pallets/werkzeug-website](https://github.com/pallets/werkzeug-website)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
