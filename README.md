# Repolex Knowledge Graph of chalk/strip-ansi

RDF knowledge graph data for [chalk/strip-ansi](https://github.com/chalk/strip-ansi), parsed by [repolex](https://repolex.ai).

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
rlex download chalk/strip-ansi
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 38ff9f2282540422031ed523f0060c7bb575e20f
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 38ff9f2282540422031ed523f0060c7bb575e20f.nq.gz
│   └── repolex
│       └── 38ff9f2282540422031ed523f0060c7bb575e20f
│           └── chunk-001.nq.gz
├── blob
│   ├── 0309635491a2e92378a7a3b381d1302c3710b197.nq.gz
│   ├── 109b692b413c4aaa57168f9a981f5fb1f48525c7.nq.gz
│   ├── 1c6314a31833395fd5ff016a6506bdd51860657c.nq.gz
│   ├── 239ecff1372358a22aa99dcbb375fdad7abba817.nq.gz
│   ├── 43c97e719a5a824700932f72e6e7e6748ce45d01.nq.gz
│   ├── 44e954d0c724d82e07bbb484f05fcbf817347b03.nq.gz
│   ├── 5358dc50b2883157fca0fa4a12d2bb18acb093ee.nq.gz
│   ├── 6313b56c57848efce05faa7aa7e901ccfc2886ea.nq.gz
│   ├── 9075c4e43fbbe2f49136c81412259d40f8b10472.nq.gz
│   ├── 93622b45c17a1c4f83bc6fe5bb41005a52b9a7bc.nq.gz
│   ├── 949e753fe64dc81ed1debff2620cbc6321b09c43.nq.gz
│   ├── a1786b3c5bc9ade04d546961a7055bc04d98c96c.nq.gz
│   ├── b591950be48f2e5521304247fa1473a68d65b23b.nq.gz
│   └── fa7ceba3eb4a9657a9db7f3ffca4e4e97a9019de.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 38ff9f2282540422031ed523f0060c7bb575e20f.nq.gz
├── filetree
│   └── 38ff9f2282540422031ed523f0060c7bb575e20f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 24 files
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

[chalk/strip-ansi](https://github.com/chalk/strip-ansi)

---
*Parsed on 2026-09-28 by [repolex](https://repolex.ai)*
