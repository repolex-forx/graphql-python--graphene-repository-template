# Repolex Knowledge Graph of graphql-python/graphene-repository-template

RDF knowledge graph data for [graphql-python/graphene-repository-template](https://github.com/graphql-python/graphene-repository-template), parsed by [repolex](https://repolex.ai).

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
rlex download graphql-python/graphene-repository-template
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 35e17a7533d9f8c65c3b5642f7f09e78f53a9fb0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 35e17a7533d9f8c65c3b5642f7f09e78f53a9fb0
│           └── chunk-001.nq.gz
├── blob
│   ├── 58d61364c140db26789ef95b9a25a8733eb9b9cc.nq.gz
│   └── efafc686ce6268e90376e7a0c401856927c118ce.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 35e17a7533d9f8c65c3b5642f7f09e78f53a9fb0.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 8 files
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

[graphql-python/graphene-repository-template](https://github.com/graphql-python/graphene-repository-template)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
