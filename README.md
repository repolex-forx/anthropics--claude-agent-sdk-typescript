# Repolex Knowledge Graph of anthropics/claude-agent-sdk-typescript

RDF knowledge graph data for [anthropics/claude-agent-sdk-typescript](https://github.com/anthropics/claude-agent-sdk-typescript), parsed by [repolex](https://repolex.ai).

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
lexq download anthropics/claude-agent-sdk-typescript
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 943af1a4eaf66649b7809d4677e2ef482467879d
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 943af1a4eaf66649b7809d4677e2ef482467879d.nq.gz
│   └── repolex
│       └── 943af1a4eaf66649b7809d4677e2ef482467879d
│           └── chunk-001.nq.gz
├── blob
│   ├── 06c15c847b2795e7a05fde75b7b1b846f026a39e.nq.gz
│   ├── 584bc7ddb3a39e0cb1a83714caa91de1436c7d5f.nq.gz
│   ├── 645a5d67c6d1e16437bec850dad5bd3b6c81f77c.nq.gz
│   ├── 675dd939c3fb327f8eb2ab73d4d56e01ed0f0daa.nq.gz
│   ├── 875320a971c8cdb7d89af55d20c5bee162d46207.nq.gz
│   ├── a151b03ef469182249bdd057bb8b5d8640c94475.nq.gz
│   ├── a25170f66b8aa2fd1e72ece6172c5a3cc11e1bc8.nq.gz
│   ├── a670c4b2b8256f07312692167ccc97153da451f6.nq.gz
│   └── fa0968cf5c3f7cf5882e21cc843c2f44ebedffdc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 943af1a4eaf66649b7809d4677e2ef482467879d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 18 files
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

[anthropics/claude-agent-sdk-typescript](https://github.com/anthropics/claude-agent-sdk-typescript)

---
*Parsed on 2026-04-16 by [repolex](https://repolex.ai)*
