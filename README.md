# Repolex Knowledge Graph of dtolnay/inventory

RDF knowledge graph data for [dtolnay/inventory](https://github.com/dtolnay/inventory), parsed by [repolex](https://repolex.ai).

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
rlex download dtolnay/inventory
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e26963a994fc389269a5f10e798cb1c87408f385
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e26963a994fc389269a5f10e798cb1c87408f385
│           └── chunk-001.nq.gz
├── blob
│   ├── 036e95d034c4aff4f8e4999ce3683fcbbe3c6a9e.nq.gz
│   ├── 039a7244ff10bd5df420355e972914b69f6ed723.nq.gz
│   ├── 12f2f4b6d703079130cfb1f22f9aa4f30e205870.nq.gz
│   ├── 190655d11ed46faec9d737f765c82d369f058f4c.nq.gz
│   ├── 1b5ec8b78e237b5c3b3d812a7c0a6589d0f7161d.nq.gz
│   ├── 23a6a065ec960a031726c8c26222b0405d4f5851.nq.gz
│   ├── 2531a3d0b15be52917e7cb2c39edcfcb7fed6e69.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 373974d1202e684e71986ec7cad7e5011832ed0c.nq.gz
│   ├── 5eff3a1c17ee79197714cfd5b992d91f5e4310ab.nq.gz
│   ├── 750707701cdae985156601cc906195021ba6a6e5.nq.gz
│   ├── 8997085ae1d4f0a5338c56b72928a5e631a4c6ff.nq.gz
│   ├── 8a43d30c151911f4bad71caf732bbfb520bd0a3b.nq.gz
│   ├── a4e6a6c6639489ba6951ee602941a1e89817500c.nq.gz
│   ├── a8f7ecdb897a825c1eb42c600e88e06dd70854e4.nq.gz
│   ├── bc028eca59881a4ecbe7b93f7fc5cf176c92d649.nq.gz
│   ├── c3347b3fcb66f01ae9e35b81ebd59ba76db58b79.nq.gz
│   ├── c8774dcf6bfa1a71ecaa855499fb5be249515120.nq.gz
│   ├── cf123832f99c35939c1b26f0cb5c79b634eebd8a.nq.gz
│   ├── e1ca89e6bd7e76cc011314cd949156b2a197aa66.nq.gz
│   ├── e9e21997b1aca0707f8749ea13c09aec66c899d2.nq.gz
│   ├── f2643a8a754592d78958c7014f418c8e33ae724f.nq.gz
│   └── f273ca2238f9cdc884c729b4c9b0259c782ccfed.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e26963a994fc389269a5f10e798cb1c87408f385.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[dtolnay/inventory](https://github.com/dtolnay/inventory)

---
*Parsed on 2026-11-09 by [repolex](https://repolex.ai)*
