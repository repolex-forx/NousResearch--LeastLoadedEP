# Repolex Knowledge Graph of NousResearch/LeastLoadedEP

RDF knowledge graph data for [NousResearch/LeastLoadedEP](https://github.com/NousResearch/LeastLoadedEP), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/LeastLoadedEP
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 411138bc1afae4e7c568c92cb9c55926701794a9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 411138bc1afae4e7c568c92cb9c55926701794a9
│           └── chunk-001.nq.gz
├── blob
│   ├── 0148ea060ee130961af8883910dd5c742ebb3a99.nq.gz
│   ├── 089a7851a40e433f9fd32ced3de02fe0bc2e2e62.nq.gz
│   ├── 2eb6a977206dcaf08cb20af7e811bc9a0387f66b.nq.gz
│   ├── 39f86ad6c0f9ba97d3fb12cfeb0e8d2288e9008e.nq.gz
│   ├── 3ec50bb7c7e163982237699723a47ee18cc1ceee.nq.gz
│   ├── 42466c829fc4d3b274eca9d2ce1cab2173fcd805.nq.gz
│   ├── 42750d756042796e6820edd4345c382450d0877d.nq.gz
│   ├── 533f8f66eb5d334f57d7f9f7aa6aa2e4fbfb75e5.nq.gz
│   ├── 747aef9d6aefc9c4705a90efe094cfee33584e66.nq.gz
│   ├── a3ce096ab347d45f52762f1f793f045c84a03942.nq.gz
│   ├── a71606dc5b30efd8cc1554624aa93a9b9a36d13b.nq.gz
│   ├── b4612a7bc59f0b1770675cc2857d866fe41a9a31.nq.gz
│   ├── c139a724672ab7e7405f9ce7717f219fee67b2a5.nq.gz
│   ├── c23a2b7a646b02a52cd17d10e5d88547507426f5.nq.gz
│   ├── dd7680688c41c4da76034544d7bda70515ed7b54.nq.gz
│   ├── de629e9f39d418866a4109e757697fc17cc4c1c0.nq.gz
│   ├── e31774df287d3b91b508341475a7cf26e146aa2d.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e9f8b00c00ecad814753d58e98ae1e43aaa49712.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 411138bc1afae4e7c568c92cb9c55926701794a9.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 26 files
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

[NousResearch/LeastLoadedEP](https://github.com/NousResearch/LeastLoadedEP)

---
*Parsed on 2026-10-09 by [repolex](https://repolex.ai)*
