# Repolex Knowledge Graph of sphinx-contrib/ogp

RDF knowledge graph data for [sphinx-contrib/ogp](https://github.com/sphinx-contrib/ogp), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/ogp
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a591bf8cb12f2a609884fd191e6ee831f22deef2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a591bf8cb12f2a609884fd191e6ee831f22deef2
│           └── chunk-001.nq.gz
├── blob
│   ├── 073a57795287eef65c5ca69d2bba7713565de9f9.nq.gz
│   ├── 15c11a42ae8028551c61f9400f682aa9e5e5e73d.nq.gz
│   ├── 17e4588013b38c5ff11b30d375dc9eff15f7db17.nq.gz
│   ├── 1bc09ba7b8bf72615328b4aafaad155f49383246.nq.gz
│   ├── 1befc1935fd429faed4778fc6db1ba52830dcf64.nq.gz
│   ├── 2a61b3751ec0e2fd68ed3eb318f672f2226e606d.nq.gz
│   ├── 2ac218e04a13fbf6d9379417282df2cad94d664b.nq.gz
│   ├── 3435e126d8da24a158fe47c5d11674c82e8a07ba.nq.gz
│   ├── 3c3c5bd468c037122e1ab996b2ef1daf4e7eea51.nq.gz
│   ├── 4877c0082c686dfdece886d67d51da7ec14d396b.nq.gz
│   ├── 51f3b9e4e7dc5586540cb60d2d859f8141acdde1.nq.gz
│   ├── 574c9162f6df14890c8c1daeacccdb90b78c5882.nq.gz
│   ├── 597a6443e697526811f72ae6c6ec17db06cc02cc.nq.gz
│   ├── 65c51c8c6d14a8f04a08469110d616762b28c50b.nq.gz
│   ├── 6d19c43466a10518dbc529f4c3183564ba291f5a.nq.gz
│   ├── 792785f2e59d82a7407a8247589be4a7a7f086f0.nq.gz
│   ├── 88628c543426624a695a0c08613c42ce6debd454.nq.gz
│   ├── 894a44cc066a027465cd26d634948d56d13af9af.nq.gz
│   ├── 984e0cb4e581f23472a2e5c8da366b83a66193a7.nq.gz
│   ├── a686b66f2f8625ecf6289828af561f6ac7392843.nq.gz
│   ├── bab0a13a75f9510f197e71867db2b6c7f1611e0a.nq.gz
│   ├── cf5f37b3dc502424ce425c49d3dd32e32ddbdf51.nq.gz
│   ├── ef2826b623a1943a46241b0d90f84b6e614d2d92.nq.gz
│   ├── f06e4063e04ce4f8ca79eee10dc7d50f965acdbc.nq.gz
│   └── f2c97b028b6b9a04bd71f181a6f45c3a5e1ae7a5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a591bf8cb12f2a609884fd191e6ee831f22deef2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 33 files
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

[sphinx-contrib/ogp](https://github.com/sphinx-contrib/ogp)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
