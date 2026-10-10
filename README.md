# Repolex Knowledge Graph of tox-dev/xml-fmt

RDF knowledge graph data for [tox-dev/xml-fmt](https://github.com/tox-dev/xml-fmt), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/xml-fmt
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── eb813b447971a7d749372894b8115258b6ba5abb
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── eb813b447971a7d749372894b8115258b6ba5abb
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d4363a8277b3af2ef040a77f2a96b886662fb13.nq.gz
│   ├── 220f93d375a19bb70914391ab389759183167d01.nq.gz
│   ├── 267eaab0147a24207d2efe59cefb25db1bc288f1.nq.gz
│   ├── 2c99416ecf9ee6402c69bead92c6b1923ab0f51a.nq.gz
│   ├── 364982344fbd94d55705e1f27a9a87abaa255333.nq.gz
│   ├── 37d037f88281baa7e7be7fe906c9ec6a3626c26e.nq.gz
│   ├── 664fdc44b51c33ade63befbbc173a0f625307da1.nq.gz
│   ├── 69d0cfd202c019ca1d5a92d59faf9a1380c61930.nq.gz
│   ├── 72e459d0e11ad20ce59e2a6e94718b1b43a9bb2b.nq.gz
│   ├── 735f80e073e97f0b7857617320b951611f826d91.nq.gz
│   ├── 8828c324d512d56c88e878db70e476494875158e.nq.gz
│   ├── 8b6c738bd641027323d6123d10b8571ca60e2a73.nq.gz
│   ├── 99d723c2f73f9e2e32cfa40365c190aeb84101f9.nq.gz
│   ├── 9d1e0987bfc323000b570d680343f00c53ddbc3d.nq.gz
│   ├── c2cf05d0c92a2fbba1204f3def316fa93bc638c3.nq.gz
│   ├── c4c7931fb1b360ea3cbb6fa3b71cc6798297fe15.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ead0d92ebb74a3f8c60d510358c5936296bbabb9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── eb813b447971a7d749372894b8115258b6ba5abb.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 25 files
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

[tox-dev/xml-fmt](https://github.com/tox-dev/xml-fmt)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
