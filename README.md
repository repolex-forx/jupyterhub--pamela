# Repolex Knowledge Graph of jupyterhub/pamela

RDF knowledge graph data for [jupyterhub/pamela](https://github.com/jupyterhub/pamela), parsed by [repolex](https://repolex.ai).

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
rlex download jupyterhub/pamela
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0894fff26692355414b6e6080acd60ed56613355
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0894fff26692355414b6e6080acd60ed56613355
│           └── chunk-001.nq.gz
├── blob
│   ├── 159436518d6eb90dd449959bd3e512ec9b01a0e4.nq.gz
│   ├── 2301d362831eab0c143a163c311837a161a58340.nq.gz
│   ├── 3f82cfa2f433a58517ea8162cfadd4e4988f2351.nq.gz
│   ├── 54a5f23be0c53b3577f2581f786359dae36724a0.nq.gz
│   ├── 619e348c41b1f5f061257d6f27a4ddb2658f9499.nq.gz
│   ├── 6cfa788d7ebe24ca190918318625539e4170cdaf.nq.gz
│   ├── a9ea5baecab8c704f36eee070e3aac6dadc6f27a.nq.gz
│   ├── aa1741d619b1863d3b525ff20505097fe3120225.nq.gz
│   ├── ab733ff2a3931fbd804bde6944811fc1821fc0b6.nq.gz
│   ├── b89dcdaefaab882f95e6d47e6ee02d774ebffca5.nq.gz
│   ├── b9258a54ab51277e6f09515ad65ee32ad7f161a7.nq.gz
│   ├── cb383e0db6fb35707caaa62ca927fbc3fa9bbf0f.nq.gz
│   ├── cc365b8c046f444d98d98bf516d9c545bc6abfec.nq.gz
│   ├── e45ef1fd5e32f39d8603a6556f65d260dc6b152a.nq.gz
│   └── fd0ebfb812868bcdd4b1dd7c3e452ad32582ce3d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0894fff26692355414b6e6080acd60ed56613355.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[jupyterhub/pamela](https://github.com/jupyterhub/pamela)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
