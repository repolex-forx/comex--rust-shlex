# Repolex Knowledge Graph of comex/rust-shlex

RDF knowledge graph data for [comex/rust-shlex](https://github.com/comex/rust-shlex), parsed by [repolex](https://repolex.ai).

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
rlex download comex/rust-shlex
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4a0724b0b62ef715467875b040a890ce75a8a829
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 4a0724b0b62ef715467875b040a890ce75a8a829.nq.gz
│   └── repolex
│       └── 4a0724b0b62ef715467875b040a890ce75a8a829
│           └── chunk-001.nq.gz
├── blob
│   ├── 151b4a2f6c83d8ea64246b90b5e577928136a445.nq.gz
│   ├── 2178ddef334d2320e362648b32240c89ac9e21d6.nq.gz
│   ├── 227431a9040c96bcf25ea427fc39919408aeb20b.nq.gz
│   ├── 36391cde5d9666a5d61b108e6d201a0f3f17a4b0.nq.gz
│   ├── 37465048a6f63d82585781a48df0c80e32aa333a.nq.gz
│   ├── 4045ed21eb844714dac9c911a200b6011cf567a6.nq.gz
│   ├── 4932db01983d38e2a17f188ce6685dffb975071b.nq.gz
│   ├── 5ec1fe1cd795faf5efa2a215813a514170a6ccfc.nq.gz
│   ├── 6400a6f75a915e70cd6c946d28db2b86aaef0b1b.nq.gz
│   ├── 654c2e9fceadb8cf3a96d32ce0d3015b74f4086f.nq.gz
│   ├── 7f299916bc6db5d97465db8c2e25188365c570f3.nq.gz
│   ├── 872c5fd47673e058bdd928ab356c31eb156a55c8.nq.gz
│   ├── 8fe176bc4e1b40dd6cc836eb620693779375631a.nq.gz
│   ├── 938d84372a16885fc24bfe4001d38b0d2c7d7e6c.nq.gz
│   ├── 94bc76618de566c4e568aaf031cce7cef592d868.nq.gz
│   ├── 95552b430bb65b33be23cbbdfde5ccda4eeeeea2.nq.gz
│   ├── a12847e41a04c22eb39cbb690dc3d69d680aa926.nq.gz
│   ├── aa5c3067af82eb996a6780f04fd9891a2567e54e.nq.gz
│   ├── abe5d8a9f9389d32e398ba9e6244034a4b7b985c.nq.gz
│   ├── aea724251913b95fe9fa94a65584c5c776fc1ced.nq.gz
│   ├── af8daad0d33c1845b9e268a8c3f4285959593f81.nq.gz
│   ├── bb6d71b82d2f6c1f04ece3fed19d99eee3207bf9.nq.gz
│   ├── c3644af34f98debc2de89a989192fdf364f5413c.nq.gz
│   ├── c7802cb0d1c91c7a90c59f78d09d44da7993ed56.nq.gz
│   ├── d36a04dded3517640bf1f409858447caa2af7195.nq.gz
│   ├── d93ed0cbf57f9eefefcb1328b17e07200b4f00d3.nq.gz
│   ├── e8fd11ffc871b6530d4272509eb4b13adc5515a6.nq.gz
│   └── fab9857bec9686b85a88b1c9631c4f9d6546d481.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4a0724b0b62ef715467875b040a890ce75a8a829.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 37 files
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

[comex/rust-shlex](https://github.com/comex/rust-shlex)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
