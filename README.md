# Repolex Knowledge Graph of asottile/ukkonen

RDF knowledge graph data for [asottile/ukkonen](https://github.com/asottile/ukkonen), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/ukkonen
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6a931aa21a7b80913659fa2caa1577205cd37e3c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6a931aa21a7b80913659fa2caa1577205cd37e3c
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c5a37eb0adeb312718e533d0a4fbcbea6880056.nq.gz
│   ├── 1962eadb1dc3e282938003e2900440c057a74ed6.nq.gz
│   ├── 1b0eda57ae27cd726758b07044bcdd0428a1e03a.nq.gz
│   ├── 3857df48f261cc023ffbbfcfd2542978ede26d76.nq.gz
│   ├── 396b9712666c81a5a47df59feccd186a16821725.nq.gz
│   ├── 5370c9485451439199ab7ab9ba30c95d9a046275.nq.gz
│   ├── 56711f2d10341d6388084d85a5560fd8b9fac96d.nq.gz
│   ├── 5ff00c89f97577ef97fc445e448a0eb79a4d1d1d.nq.gz
│   ├── 7e451508b607bbd6c23b3fdd025fb86fffa922cf.nq.gz
│   ├── 8904f8f069f8caa31c6f10fc80f5a6cdb60e49a9.nq.gz
│   ├── 890f66cd81c1371c9340f40d679e3e9be0b85367.nq.gz
│   ├── b1447c3015af9511f2dee402ca4b5ad62adf5dce.nq.gz
│   ├── bdf2bf215a4187d259500f52eef1cad697b92eb3.nq.gz
│   ├── d29ee2cb2c2eb47beddb095c2f658904a41182f0.nq.gz
│   ├── dd199527135d8c4c88cd6963b2eba89b16ccb864.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ecb47fcbb095527e947479366f25dcffcf465631.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6a931aa21a7b80913659fa2caa1577205cd37e3c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[asottile/ukkonen](https://github.com/asottile/ukkonen)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
