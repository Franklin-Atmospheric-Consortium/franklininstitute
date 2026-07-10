# Franklin Atmospheric Consortium

A historical research project exploring Benjamin Franklin's pioneering work in atmospheric science and climate, tracing the evolution of these fields from the 18th century through the early 20th century.

## About This Repository

This repository follows the **LLM Wiki pattern** - a system for building and maintaining personal knowledge bases using LLMs. Rather than just storing documents, the LLM incrementally builds and maintains a structured, interlinked wiki that synthesizes information across sources.

## Structure

```
/
├── raw/                    # Source documents (immutable)
│   └── [historical documents, papers, articles]
├── wiki/                   # LLM-maintained wiki (structured knowledge)
│   ├── index.md           # Content catalog
│   ├── log.md             # Chronological activity log
│   ├── overview.md        # High-level synthesis
│   ├── entities/          # People, organizations, places
│   ├── concepts/          # Scientific concepts and theories
│   ├── sources/           # Source summaries
│   └── topics/            # Thematic syntheses
├── CLAUDE.md              # Schema defining wiki structure and workflows
├── llm-wiki.md            # Pattern documentation
└── README.md              # This file
```

## How It Works

### Three Layers

1. **raw/** - Your curated collection of source documents. These are immutable - the LLM reads from them but never modifies them.

2. **wiki/** - LLM-generated and maintained markdown files. The LLM creates summaries, entity pages, concept pages, and maintains cross-references. This is where knowledge is synthesized and structured.

3. **CLAUDE.md** - The schema file that tells the LLM how the wiki is structured, what conventions to follow, and what workflows to use.

### Key Operations

**Ingest**: Process a new source document. The LLM reads it, creates a summary, updates relevant entity and concept pages, and maintains the index.

**Query**: Ask questions against the wiki. The LLM searches relevant pages and synthesizes answers with citations.

**Lint**: Health-check the wiki for contradictions, stale claims, missing cross-references, and gaps.

## Getting Started

### For Humans

1. **Browse the wiki**: Start with `wiki/overview.md` for a high-level synthesis
2. **Check the index**: `wiki/index.md` catalogs all pages by category
3. **Follow the links**: Wiki pages are heavily cross-referenced - follow connections
4. **View in Obsidian**: For the best experience, open this repo in Obsidian to see the graph view and navigate links

### For LLMs

1. **Read CLAUDE.md**: This defines the wiki structure and your workflows
2. **Check wiki/log.md**: See what's been done recently
3. **Read wiki/index.md**: Find relevant pages for queries
4. **Follow the workflows**: Ingest sources, answer queries, maintain the wiki

## Current Status

**Wiki initialized** - The structure is in place and ready for source ingestion. Six historical documents are in `raw/` awaiting processing.

## The Franklin Mystery

Benjamin Franklin was investigating two connected phenomena from 1783-1784:

1. A strange "dry fog" that covered much of Europe during summer 1783
2. An exceptionally harsh winter that followed in 1783-1784

Franklin proposed that the fog (caused by volcanic eruptions, particularly Lakagígar in Iceland) reduced the sun's heating effect, leading to the severe winter. This was remarkably prescient - modern science has confirmed the connection between volcanic aerosols and climate patterns.

This repository traces the development of atmospheric and climate science from Franklin's early observations through the formalization of greenhouse gas theory in the late 19th century.

## Tools & Recommendations

- **Obsidian**: Best way to browse and visualize the wiki (graph view, link navigation)
- **Obsidian Web Clipper**: Browser extension for converting web articles to markdown
- **Git**: The wiki is version controlled - you get history and collaboration for free

## Learn More

- See `llm-wiki.md` for detailed documentation of the LLM Wiki pattern
- See `CLAUDE.md` for the specific schema and workflows for this wiki
- See `wiki/overview.md` for a synthesis of the current knowledge base

## License

This is a research and educational project. Source documents are historical and in the public domain where applicable.
