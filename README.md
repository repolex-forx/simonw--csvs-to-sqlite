# Repolex Knowledge Graph of simonw/csvs-to-sqlite

RDF knowledge graph data for [simonw/csvs-to-sqlite](https://github.com/simonw/csvs-to-sqlite), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/csvs-to-sqlite
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 33b79ed80a688ceae4486ebdcca28ae689f54c03
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 33b79ed80a688ceae4486ebdcca28ae689f54c03
│           └── chunk-001.nq.gz
├── blob
│   ├── 09493a0327824162e87b231905491d1ad5535fc1.nq.gz
│   ├── 0b5e353f75269c2e282b4d5f2134dcb4d12a771f.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 310f0f3852ae6a6edc5f5e4191b9c8ea4d8608e1.nq.gz
│   ├── 3c535d72a8ac98d2573c7c54061bf7c7e6273b98.nq.gz
│   ├── 50951b3967c5319e170182fa7ed198393115a2c3.nq.gz
│   ├── 6f737b22fb6ac417e9e5e5e5c0fa739a0d54b592.nq.gz
│   ├── a5dd7e90cade8266d18389e09b329d97f5ef9aea.nq.gz
│   ├── b822625a6955e15b49c11f1071f4f13966e0a108.nq.gz
│   ├── c7014155928cd02b3d1db6b2a3a295e10e7bfb73.nq.gz
│   ├── e248aa3b7087d6a5b27c87eb2b7a4b641b50941e.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f05f93325bd3df2f08e1e3ce01cc735762195936.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 33b79ed80a688ceae4486ebdcca28ae689f54c03.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[simonw/csvs-to-sqlite](https://github.com/simonw/csvs-to-sqlite)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
