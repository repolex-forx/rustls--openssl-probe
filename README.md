# Repolex Knowledge Graph of rustls/openssl-probe

RDF knowledge graph data for [rustls/openssl-probe](https://github.com/rustls/openssl-probe), parsed by [repolex](https://repolex.ai).

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
rlex download rustls/openssl-probe
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9181752ff5eab32339111dbdcc6cdc9f5a5eb06e
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 9181752ff5eab32339111dbdcc6cdc9f5a5eb06e.nq.gz
│   └── repolex
│       └── 9181752ff5eab32339111dbdcc6cdc9f5a5eb06e
│           └── chunk-001.nq.gz
├── blob
│   ├── 0198966c4add904da8f042f32b858403553f2f6f.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 39e0ed6602151f235148e6c08413aa7eda5b9038.nq.gz
│   ├── 3f6dd57ef3ae9fac4c60feda8bd6739ce083e6f9.nq.gz
│   ├── 83b6baec6aa61ccd28bdd497e20ee5f441655762.nq.gz
│   ├── 9730df5fbfcb14a0d954914d442fd1e92398cf70.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── aa79cd5af8f2d8c5f7f497ffad949847495b537a.nq.gz
│   └── e7a5f5756e0274e9652b823c82d73b2fcdf4da55.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9181752ff5eab32339111dbdcc6cdc9f5a5eb06e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 18 files
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

[rustls/openssl-probe](https://github.com/rustls/openssl-probe)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
