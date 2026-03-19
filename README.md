# Repolex Knowledge Graph of supermodeltools/bigiron

RDF knowledge graph data for [supermodeltools/bigiron](https://github.com/supermodeltools/bigiron), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download supermodeltools/bigiron
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fb33f8e91e9d12f4e063f703846c71638af0c5c5.nq.gz
│   ├── lsp
│   │   └── fb33f8e91e9d12f4e063f703846c71638af0c5c5.nq.gz
│   └── repolex
│       └── fb33f8e91e9d12f4e063f703846c71638af0c5c5.nq.gz
├── blob
│   ├── 0d56bf391133e337877b8c0739a9427c85b881d9.nq.gz
│   ├── 11d186d0e334ee89f820b8df36900274f064d955.nq.gz
│   ├── 1c426454319007b3c9e3305a3c9834ba057530e1.nq.gz
│   ├── 1cea821d3913aac3e7d9b1d79650bc3c0c1b8f5c.nq.gz
│   ├── 2305a454770edeb42d8b2c0a002d0cb24f099252.nq.gz
│   ├── 3044eb2dd17394a9d361c5b8f9a06361376a355d.nq.gz
│   ├── 36b999aa409b787459c6a03b839c88179ce3a337.nq.gz
│   ├── 3754ee449ca0f3b977a677be9a5ae50d73d62101.nq.gz
│   ├── 37f530adc5a6180589addd4c5fed26c0301982cb.nq.gz
│   ├── 38ecfec18124db8588658c6831a5436f315eb8f3.nq.gz
│   ├── 3a66e46fc65ec53819a3ac745a9657efaa5fd4d3.nq.gz
│   ├── 4af84a4cde130e7a4ef0c0a9fae127935285ff87.nq.gz
│   ├── 5eea6be8d16b3da261a602a3678b003bb9f57af6.nq.gz
│   ├── 6ddc5964e84f4c721aa479a13e89785c9e3498ca.nq.gz
│   ├── 7adb800176aa860774e78d8c2da94ad9636a17a5.nq.gz
│   ├── 81e5581563003597138e7029f1ac0b4cc8bbe779.nq.gz
│   ├── 85f732c1c1f8bd224b0f2ae64d053d3c067a1989.nq.gz
│   ├── 88873c999d37309e2817240db4f74a8d6824f3ef.nq.gz
│   ├── 895cf375137f43b45b06e591cdcddc6874281353.nq.gz
│   ├── 955178c4ebf0f141b2a89acc6882563fda4c7049.nq.gz
│   ├── 9b820b2e3a53327a4a392b9cfcb4831f5db0ca93.nq.gz
│   ├── a7e4c8fcfe81c4e1bd42c5d863dc266ab171be97.nq.gz
│   ├── ac917afd27f87fe84bb4fb6c57a2fbe74f4e1a64.nq.gz
│   ├── aebc0ca2a9658a4885d4b97cb272b15c44bf1631.nq.gz
│   ├── c1d9945c78dfe657409f3b777c69ce5bf7be1b24.nq.gz
│   ├── c4fdff4ad0bc6b088db16edf65ae49456b69ae2e.nq.gz
│   ├── d7b2b6a023a0991673a33524288b12455c603a8f.nq.gz
│   ├── e3f097082139200e97edc0accf454e0fda2a0271.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e9043178798e3ab1bb05593ae0d55cb456037559.nq.gz
│   ├── e943c9f7471225cf71bcba7bc6f0fbeb49fb2219.nq.gz
│   ├── ebf1625f0fc35afd76c3f089f92d86c12fd631da.nq.gz
│   └── f35dd3e12d888f90715afdf5931bd68cbbf4d786.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── fb33f8e91e9d12f4e063f703846c71638af0c5c5.nq.gz
├── filetree
│   └── fb33f8e91e9d12f4e063f703846c71638af0c5c5.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 41 files
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

## Source repository

[supermodeltools/bigiron](https://github.com/supermodeltools/bigiron)

---
*Parsed on 2026-03-19 by [repolex](https://repolex.ai)*
