# Repolex Knowledge Graph of softprops/atty

RDF knowledge graph data for [softprops/atty](https://github.com/softprops/atty), parsed by [repolex](https://repolex.ai).

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
rlex download softprops/atty
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7b5df17888997d57c2c1c8f91da1db5691f49953
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 7b5df17888997d57c2c1c8f91da1db5691f49953.nq.gz
│   └── repolex
│       └── 7b5df17888997d57c2c1c8f91da1db5691f49953
│           └── chunk-001.nq.gz
├── blob
│   ├── 3b3635e59cbd1d11fe3e6e415e883e2cdc7a7581.nq.gz
│   ├── 4e9673f0de20b5819c41bb7d12a029a57ab62b30.nq.gz
│   ├── 501cad69484a700012b21d5963524e16cf9932e2.nq.gz
│   ├── 899a094cd597781dd1fa2de7ac9a84af30df2da1.nq.gz
│   ├── a628724c98f70517e960bc9aa849a7a8916c0675.nq.gz
│   ├── aa2cbb77e1ee7ed6e93d241da3e1bf442dacffd3.nq.gz
│   ├── afc9901273ce4b9b2e28f157ab49879a5be61f9a.nq.gz
│   ├── b9da76b73525c7e771eeebdb5514abcb00326564.nq.gz
│   ├── cd85593d6e0cd22435a079e02ea5ca94e64bf203.nq.gz
│   └── d7fb127948abdaeff5c993f94dca312e08cf3858.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 7b5df17888997d57c2c1c8f91da1db5691f49953.nq.gz
├── filetree
│   └── 7b5df17888997d57c2c1c8f91da1db5691f49953.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 20 files
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

[softprops/atty](https://github.com/softprops/atty)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
