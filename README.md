# Repolex Knowledge Graph of block/homebrew-tap

RDF knowledge graph data for [block/homebrew-tap](https://github.com/block/homebrew-tap), parsed by [repolex](https://repolex.ai).

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
rlex download block/homebrew-tap
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 58eb90012beed930fcc0a7a7cc16077bbf66b64e
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 58eb90012beed930fcc0a7a7cc16077bbf66b64e.nq.gz
│   └── repolex
│       └── 58eb90012beed930fcc0a7a7cc16077bbf66b64e
│           └── chunk-001.nq.gz
├── blob
│   ├── 08774c192448503f586cd58b47c36b29a9a10b1c.nq.gz
│   ├── 0884f781ebd3bab25a86398a263ce1ea0d21040d.nq.gz
│   ├── 0917bf670fd2f09c0040b492ed8aaaa322a31678.nq.gz
│   ├── 0b0cdc633a54024d092fa968020929273b881d8a.nq.gz
│   ├── 10f5d0f97c30c6be2e27e64b497bdf829b338eda.nq.gz
│   ├── 1aa350602b3e6c5f167832aa74817ed38faa5e5b.nq.gz
│   ├── 1bc0931362a83e952ddec5e8de3c4275daad8939.nq.gz
│   ├── 1bc469e68eb776aa52185c6cbfc5cdcaee837ce3.nq.gz
│   ├── 1ff0ac691da62ec1c093b5df424514e3c113eaf3.nq.gz
│   ├── 26fdeeeea1464604f30f7038c8bf1a23462334b5.nq.gz
│   ├── 31cf63ff9a9b8b2a53eb0825511186ed5957f429.nq.gz
│   ├── 3bde45bf02ca115356a7020b1927c42365b5210a.nq.gz
│   ├── 40018ee945cf408083e8bd75538911689e7308c3.nq.gz
│   ├── 4e02a26d58a68504559db3f51a3ea6abfd304a42.nq.gz
│   ├── 589e6cf6634402fc297be678b48e717487355793.nq.gz
│   ├── 59525ccba38d9fec6f4a31efcd3536d58f8816e6.nq.gz
│   ├── 6087cfc757a25d1b624a17c926241d89e98fafad.nq.gz
│   ├── 647a8e93b3e8b0e849a37308eb1473aec95c784b.nq.gz
│   ├── 6bccf43368fd7c96d9c659562a5142b8b8cb98a1.nq.gz
│   ├── 7bf2b54e6b1a26c7a624cf8ea59676f9b177e3d9.nq.gz
│   ├── 7e0e3863c389c6585bcf656e02d82a51ff686b1c.nq.gz
│   ├── 82198f8f449bee10df8450993371e5ea915554c8.nq.gz
│   ├── 852f237319adbd83bd8b0b5b3eec9181348b178a.nq.gz
│   ├── 89dce43a11731be961b84cd20f76811f4bd74c21.nq.gz
│   ├── 8b6c16c74007a49132e17e0ccb50c264ad962d09.nq.gz
│   ├── b027c703c79bbb01138be3b0b458562994521b36.nq.gz
│   ├── b27fb44d4b743e3caca0da034ce916564eca30ca.nq.gz
│   ├── c910315f3751019d872c272702fef7c0dc18902b.nq.gz
│   ├── cc0237c5671569dc312f9f4559a228b25dbb3a75.nq.gz
│   ├── e832116613d5b4b6f3d5993fe550601819cfecab.nq.gz
│   ├── ec048bed1dc9adbffa6adf907fe386674743a802.nq.gz
│   ├── ed162d9d8ca7b0859b5ed22b17d87184b917d023.nq.gz
│   ├── f3675e2b7206ae0843099cc82d77af83313860b1.nq.gz
│   ├── f621ce4f01cc652d47d524d13c7714832c291e2b.nq.gz
│   ├── fa376f0943df26c4e2d24fc2c6bc14ec142685a5.nq.gz
│   ├── fbeb057de6a23649fbf30b440f6067da1f972377.nq.gz
│   └── fd73d837c6d088869346ec68829675a43910bc51.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 58eb90012beed930fcc0a7a7cc16077bbf66b64e.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 45 files
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

[block/homebrew-tap](https://github.com/block/homebrew-tap)

---
*Parsed on 2026-10-08 by [repolex](https://repolex.ai)*
