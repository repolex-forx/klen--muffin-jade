# Repolex Knowledge Graph of klen/muffin-jade

RDF knowledge graph data for [klen/muffin-jade](https://github.com/klen/muffin-jade), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-jade
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3ddd6bf27fac03edc0bef3b0840bcd2e278babb3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3ddd6bf27fac03edc0bef3b0840bcd2e278babb3
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b2e907c89333ea1b1c45cf476f5afdd63c69c08.nq.gz
│   ├── 1e32f2976210f83d472e6524322dc8a06a540fe7.nq.gz
│   ├── 32e98313ac876fd826fb6d758fafd1e12251b117.nq.gz
│   ├── 4c825f396d4db90f442599e13a55c1a39bfca651.nq.gz
│   ├── 5544235edebf7bf6c7a18ccdd5c721a6acbfff49.nq.gz
│   ├── 5aae96c05508cd2a35f42796ae1ba37d3ea22e0b.nq.gz
│   ├── 5fd63afacfafb2e238d3293418636944ab64d2f1.nq.gz
│   ├── 622d1b849a986d41a8c972a70e3d53a2ca9e5179.nq.gz
│   ├── 653627ed6e6933039b28b895aa9f4403382c6269.nq.gz
│   ├── 7d08efd721e5e56a84b945cd6b2790c6f03c2fb4.nq.gz
│   ├── 7fc9cdf2c22d72df5cdd290f86f135ca7eb4c9dd.nq.gz
│   ├── 86785a7ee375534ef6e7d2e938d89dc137b7ecaf.nq.gz
│   ├── 93b3bff2b78ac76a586ec2f94b4f792cb7cd4f5a.nq.gz
│   ├── 9b9b709de37672ffdbdb7b7573294afa3bca3160.nq.gz
│   ├── 9c69457bf1ff331090833d031badb7027d329363.nq.gz
│   ├── a3b5fc4ec6fb06670f0e626fc64f3ebcf3ec4d34.nq.gz
│   ├── a8b2cab8622b598e6fb380e1fec17ec9408593e5.nq.gz
│   ├── d844cc184ff61c05717c0636249878e411419acf.nq.gz
│   └── ee1072d412e2d14e9f2b114c16111171b14462e4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3ddd6bf27fac03edc0bef3b0840bcd2e278babb3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[klen/muffin-jade](https://github.com/klen/muffin-jade)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
