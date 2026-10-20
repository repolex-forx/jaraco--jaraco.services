# Repolex Knowledge Graph of jaraco/jaraco.services

RDF knowledge graph data for [jaraco/jaraco.services](https://github.com/jaraco/jaraco.services), parsed by [repolex](https://repolex.ai).

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
rlex download jaraco/jaraco.services
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4a2b87afec29171912076c260f05f577586b7e98
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4a2b87afec29171912076c260f05f577586b7e98
│           └── chunk-001.nq.gz
├── blob
│   ├── 10d412f406891b9683f832fcbc134c9bdf4f916e.nq.gz
│   ├── 1f2aa7533b0423a8eb943f6f4ec02498e39581a0.nq.gz
│   ├── 240329c3604d8ead4c10aa8c88352caa8e4ce7b2.nq.gz
│   ├── 2e3f4dd791a6372b427d618eb0baa8c4dc58e5f0.nq.gz
│   ├── 304196f81e11a168c9894f966e4a617ebf4ed53c.nq.gz
│   ├── 54c9000ec94341dd65c2053251b85b124017b9b5.nq.gz
│   ├── 54cc8303b22089e12053e552d4e6cb852a865b8a.nq.gz
│   ├── 577e87a793a20e413f7321f4f17ec1eba2ea1962.nq.gz
│   ├── 5bdc232005af9be104a00437ae9bc64417a4c1cc.nq.gz
│   ├── 700235be57c1b2872455c0be5333f59cf568e252.nq.gz
│   ├── 724370638fc188317bbc7dc868f1a571995fd796.nq.gz
│   ├── 8e8a09e98cfdaa1b97bee5d213db699f94424590.nq.gz
│   ├── 8f0a0194dd595fc8714eaf00f13c30188c35437f.nq.gz
│   ├── 9a0f3bce1395ae3819030b822e5d9076c85068ea.nq.gz
│   ├── 9f7aefd729710140efe12f62643cc83e260ec8e2.nq.gz
│   ├── b5afdf89640230fa532090d39dac390f8e16c2a8.nq.gz
│   ├── beaf80eeba85217a30643f7b1367d16758151069.nq.gz
│   ├── d07b7592987f724351fd1e2ad6dec88eb0c92c8a.nq.gz
│   ├── d5da4fc65307a861989ced2b2d66d95839fb2ec4.nq.gz
│   ├── e05a3d4a2ab888e32952006d8cd380864368db5f.nq.gz
│   └── efcb8cbc2043faa7caf4f92fc7488bd6914c934c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4a2b87afec29171912076c260f05f577586b7e98.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[jaraco/jaraco.services](https://github.com/jaraco/jaraco.services)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
