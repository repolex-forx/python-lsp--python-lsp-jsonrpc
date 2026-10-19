# Repolex Knowledge Graph of python-lsp/python-lsp-jsonrpc

RDF knowledge graph data for [python-lsp/python-lsp-jsonrpc](https://github.com/python-lsp/python-lsp-jsonrpc), parsed by [repolex](https://repolex.ai).

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
rlex download python-lsp/python-lsp-jsonrpc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a96d764d29cc17fbda52264e529f0803cda07fd8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a96d764d29cc17fbda52264e529f0803cda07fd8
│           └── chunk-001.nq.gz
├── blob
│   ├── 03314c630bafedce6a81a9d641845e76b21dd5d1.nq.gz
│   ├── 03e10f94cdedfb156eef49151a1291afa12a688e.nq.gz
│   ├── 08fb62da96e76146897332ca9155d7ade7e6167a.nq.gz
│   ├── 0c9e62a30578a1f7d3f617e8542cac61f4c3af8b.nq.gz
│   ├── 13fe9e1d593619e4010a0529cb2d94ce197669da.nq.gz
│   ├── 1430490f097b60db802c00ae82bad4bdd0d37671.nq.gz
│   ├── 14fe1bb8fedcb6133094c67a04e29cb46e7514c7.nq.gz
│   ├── 3371a20559d38dc073f4721b20bd09c3e436101e.nq.gz
│   ├── 376785c779721bfd8f307cb3f30ea6e9a74523e0.nq.gz
│   ├── 37848896aa0c0601c9aa722fc781776228772552.nq.gz
│   ├── 40048a9a26d20e4214a5c9187efa6f6102707699.nq.gz
│   ├── 45bc81ae8ce520668e45b2b5966e3791c351d4b8.nq.gz
│   ├── 56a66375716a5814265641404c004e35911ac856.nq.gz
│   ├── 6811279944f9381268992fedce7e77e6627c82e1.nq.gz
│   ├── 6dc565b96af324bb98c420c60a1b396b8dad6588.nq.gz
│   ├── 729e41355a050e1c8f9c7b09a2f8a91ebfad8ad6.nq.gz
│   ├── 846c70fd606933c1c6cbf372008954d7153feb65.nq.gz
│   ├── 933ff6a4f7f3344e80f9f2877d72eec588b26151.nq.gz
│   ├── 95df41c147f824b507238d26a529081b17656aa9.nq.gz
│   ├── a089f1ba032cf9278866e8cf1881b75506218e98.nq.gz
│   ├── a0fcbce3c7bd280f82b2a3bbf02891c9b63b6ccd.nq.gz
│   ├── a1ddc8fe8263c8f7a7d33dd59a840cb912c1d412.nq.gz
│   ├── db5f20e90ac6cc89cbd7b867d1b8f78c58727ef7.nq.gz
│   ├── e0c9525ad8f3ea1dea49ef26e2cb87e12f149921.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ed70640d2693aa8e43a42cc8ebd54801bdf93658.nq.gz
│   └── ef4135507e5c1f56922f1102bad79908b6bd4414.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a96d764d29cc17fbda52264e529f0803cda07fd8.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 35 files
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

[python-lsp/python-lsp-jsonrpc](https://github.com/python-lsp/python-lsp-jsonrpc)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
