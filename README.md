# Repolex Knowledge Graph of falconry/pygments-theme

RDF knowledge graph data for [falconry/pygments-theme](https://github.com/falconry/pygments-theme), parsed by [repolex](https://repolex.ai).

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
rlex download falconry/pygments-theme
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ba5b169902b80eac086c2d412d5e111920bce5e3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ba5b169902b80eac086c2d412d5e111920bce5e3
│           └── chunk-001.nq.gz
├── blob
│   ├── 0455085090e7256744ef1d4bf32aa15bce4d1765.nq.gz
│   ├── 1f2f817a691c98994aedc5e6d83bd9f16dc77ee2.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 4b8e91eb83602e28ce6a09618b587a1072f224a1.nq.gz
│   ├── 67af5b334acadf1510414ce7740f3ebf7690ae7f.nq.gz
│   ├── 89d13d96d9a3a015707a1cb989b8f50779848257.nq.gz
│   ├── 91fbc62ce9b1188c14abdda000d6e6cc3716f7b7.nq.gz
│   ├── a19d19d927993eb53e84876f36622a249b9f8088.nq.gz
│   ├── ab245606bab53234cc3a341e342c93c0a381fd97.nq.gz
│   ├── bcb58d0bfb792aade6f21c2a624078148c4d1782.nq.gz
│   ├── c5fb95bfd5ef080f6e51f48b28a6e5459ab87f81.nq.gz
│   ├── d1b246bbd2301795610c8e5aa803669c2256fb14.nq.gz
│   ├── d1e7199fb8bb42a68289f4cf9570e24b96ea93e9.nq.gz
│   ├── d4db5078e4ea6f3cd3f656f57d4dd11515859211.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f29210988897229bede86c7db42e980fce8b6be7.nq.gz
│   └── f3c5ecab480d2677c0fa13daae96b71755fec33b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ba5b169902b80eac086c2d412d5e111920bce5e3.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 24 files
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

[falconry/pygments-theme](https://github.com/falconry/pygments-theme)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
