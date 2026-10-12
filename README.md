# Repolex Knowledge Graph of Pylons/pyramid_handlers

RDF knowledge graph data for [Pylons/pyramid_handlers](https://github.com/Pylons/pyramid_handlers), parsed by [repolex](https://repolex.ai).

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
rlex download Pylons/pyramid_handlers
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b5023e666e22f4e81e0a3db43d682be227d2a737
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b5023e666e22f4e81e0a3db43d682be227d2a737
│           └── chunk-001.nq.gz
├── blob
│   ├── 104915791a3361c47cb21f4bb648d65450e3d520.nq.gz
│   ├── 14eac727f9f82835a2e62eb65139674f85f1f7f3.nq.gz
│   ├── 178e49f67b79e740fbd6916b4434a922df97a9a1.nq.gz
│   ├── 19e8ac13562e26d3a3ddd29b531eca8c1327d88b.nq.gz
│   ├── 2f536a1d06a98e5e37d949368473cc96eabe6ff1.nq.gz
│   ├── 311e0b38fcd5ced74a7a7b1f25a46d161f03af25.nq.gz
│   ├── 35937a39e2019c7e32508557d80f093006bb1867.nq.gz
│   ├── 3aa379e13e267519be43e22a037f14d97cf7a6e1.nq.gz
│   ├── 45397942b83286ce88935062a1afd441b8215998.nq.gz
│   ├── 6471b03cfa08183bb5f1f34ef76296427b88be06.nq.gz
│   ├── 69fa449dd96e2405945b2e4cff2fd0ab8b102097.nq.gz
│   ├── 6ef508fc0a6d3c0de598cc141b8297d166c99cf9.nq.gz
│   ├── 8e0e0466e228f7974a64c3abf77865f37dc34ea8.nq.gz
│   ├── 9f19ebd142bfaf48868e03b859843fa0c0951dd2.nq.gz
│   ├── a88c60c5d98173857df42c603a7743589bd6810d.nq.gz
│   ├── b3b1cdc3a96127119a38ca3acd771db557873072.nq.gz
│   ├── b6abd03d6e5801fc7bf45f74ec76fc220280c6aa.nq.gz
│   ├── b6e116402587928cce6513b148840586c263b464.nq.gz
│   ├── be22d2c3de5cb30e8c4774a5f539cb0690739b04.nq.gz
│   ├── e002fbd7290a6a03cf1ed24d560931ed5af4974d.nq.gz
│   ├── e075f1a95797b8542a64ae627f62e2a56205ff6b.nq.gz
│   ├── ea7111c148df21c229593f2d523596411dda19a7.nq.gz
│   ├── f4eb4ef03531cc8d542efa457d2880e2c8e3ec49.nq.gz
│   ├── f4f9563b986b028b2d6cb0a7a3a06ef31e72df83.nq.gz
│   ├── fa8d791a20febfa77adf304a8a75f6b644260a38.nq.gz
│   └── fcbc735be60b2d6b66f36aae402bd2b59759a99c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b5023e666e22f4e81e0a3db43d682be227d2a737.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[Pylons/pyramid_handlers](https://github.com/Pylons/pyramid_handlers)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
