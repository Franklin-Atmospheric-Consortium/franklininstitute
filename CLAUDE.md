# Claude Schema for Franklin Institute Wiki

## Purpose

This is the Franklin Institute Archives - a historical knowledge base documenting the development of atmospheric science and intervention from Benjamin Franklin's pioneering 1784 observations through the establishment of modern atmospheric commerce in the early 20th century.

**CRITICAL: In-Universe Perspective**

This wiki is written from within an alternate history timeline. All content maintains an in-universe voice, treating the alternate history as actual history. The wiki presents itself as a genuine historical archive from a world where Benjamin Franklin conducted the first atmospheric intervention experiment in 1785, leading to a century of atmospheric management infrastructure development before Svante Arrhenius's 1896 greenhouse effect calculations found immediate practical application.

## Architecture

This repository follows the LLM Wiki pattern with three layers:

1. **raw/** - Immutable source documents (articles, papers, historical documents, research notes)
2. **wiki/** - LLM-maintained markdown files (summaries, entity pages, concept pages, synthesis)
3. **CLAUDE.md** - This schema file defining structure and workflows

## Directory Structure

```
/
├── raw/                    # Source documents (immutable)
│   └── [source files]
├── wiki/                   # Wiki pages (LLM-maintained)
│   ├── index.md           # Content catalog
│   ├── log.md             # Chronological activity log
│   ├── overview.md        # High-level synthesis
│   ├── entities/          # People, organizations, places
│   ├── concepts/          # Scientific concepts, theories
│   ├── sources/           # Source summaries
│   └── topics/            # Thematic pages
├── CLAUDE.md              # This schema file
├── llm-wiki.md            # Pattern documentation
└── README.md              # Project introduction
```

## Page Types

### Source Summaries (wiki/sources/)
- One page per source document in raw/
- Filename: `[source-name].md`
- Structure:
  - **Source**: Link to raw file
  - **Date**: When the source was created/published
  - **Type**: (historical document, paper, article, etc.)
  - **Nature**: Historical or Alternate History
  - **Summary**: Key points and findings
  - **Key Entities**: People, places, organizations mentioned
  - **Key Concepts**: Scientific concepts discussed
  - **Connections**: Links to related wiki pages
  - **Quotes**: Notable excerpts

### Entity Pages (wiki/entities/)
- People, organizations, places
- Filename: `[entity-name].md`
- Structure:
  - **Type**: Person/Organization/Place
  - **Dates**: Birth-death, founding, etc.
  - **Overview**: Brief description
  - **Role in Project**: Relevance to Franklin Atmospheric Consortium
  - **Key Contributions**: Main ideas, discoveries, work
  - **Mentioned In**: Links to sources
  - **Related Entities**: Cross-references
  - **Related Concepts**: Scientific concepts connected to this entity

### Concept Pages (wiki/concepts/)
- Scientific theories, phenomena, methods
- Filename: `[concept-name].md`
- Structure:
  - **Definition**: Clear explanation
  - **Historical Context**: When/how it emerged
  - **Key Figures**: Who developed/studied it
  - **Evolution**: How understanding changed over time
  - **Mentioned In**: Links to sources
  - **Related Concepts**: Cross-references

### Topic Pages (wiki/topics/)
- Thematic syntheses across multiple sources
- Filename: `[topic-name].md`
- Structure:
  - **Overview**: What this topic covers
  - **Key Questions**: Central questions explored
  - **Historical Development**: Timeline of understanding
  - **Key Sources**: Primary documents
  - **Synthesis**: Integrated analysis
  - **Open Questions**: Gaps or areas for further research

### Overview (wiki/overview.md)
- High-level synthesis of the entire knowledge base
- Updated as major new sources are added
- Structure:
  - **Project Summary**: What the Franklin Atmospheric Consortium is about
  - **Timeline**: Major events and developments
  - **Key Themes**: Overarching patterns
  - **Major Figures**: Most important people
  - **Core Concepts**: Central scientific ideas
  - **Current State**: What we know so far

## Workflows

### Ingest a New Source

1. **Read** the source document from raw/
2. **Discuss** key takeaways with user
3. **Create** source summary page in wiki/sources/
4. **Update** or create entity pages for people, places, organizations mentioned
5. **Update** or create concept pages for scientific ideas discussed
6. **Update** relevant topic pages with new information
7. **Update** wiki/index.md with new pages
8. **Update** wiki/overview.md if this is a significant addition
9. **Append** entry to wiki/log.md with format: `## [YYYY-MM-DD] ingest | [Source Name]`

### Answer a Query

1. **Read** wiki/index.md to find relevant pages
2. **Read** relevant wiki pages
3. **Synthesize** answer with citations to wiki pages and sources
4. **Consider** if answer should be filed as a new wiki page (comparison, analysis, synthesis)
5. If filing: create page, update index, append to log

### Lint the Wiki

1. **Check** for contradictions between pages
2. **Identify** stale claims superseded by newer sources
3. **Find** orphan pages with no inbound links
4. **Suggest** missing concept pages for frequently mentioned ideas
5. **Identify** missing cross-references
6. **Note** data gaps that could be filled
7. **Suggest** new questions to investigate

### Update Existing Pages

When new information affects existing pages:
- Add new information with source citations
- Note contradictions explicitly (don't silently overwrite)
- Update "Last Updated" date in frontmatter
- Maintain chronological integrity

## Conventions

### Links
- Use wiki-style links: `[[Page Name]]`
- Link generously - every entity/concept mention should link to its page
- Prefer descriptive link text over bare URLs

### Citations
- Format: `[Source Name](../raw/filename.md)` for raw sources
- Format: `[[Source Summary]]` for wiki source pages
- Include page numbers or sections when relevant

### Frontmatter
Use YAML frontmatter for metadata:
```yaml
---
type: [entity|concept|source|topic|overview]
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags: [tag1, tag2]
---
```

### Dates
- Use ISO format: YYYY-MM-DD
- For historical dates, use format: [YYYY-MM] or [YYYY] when month/day unknown

### Naming
- Use descriptive, readable filenames
- Separate words with hyphens: `atmospheric-science.md`
- Match page titles to filenames (except for capitalization)

## Log Format

Each log entry should follow this format:
```
## [YYYY-MM-DD] [operation] | [description]

[Brief details about what was done]
- Created: [list of new pages]
- Updated: [list of updated pages]
```

Operations: `ingest`, `query`, `lint`, `refactor`, `init`

## Index Format

Organize by category with links and one-line descriptions:
```markdown
## Sources
- [[Source Name]] - Brief description (YYYY-MM-DD)

## Entities
### People
- [[Person Name]] - Brief description (dates)

### Organizations
- [[Org Name]] - Brief description

### Places
- [[Place Name]] - Brief description

## Concepts
- [[Concept Name]] - Brief description

## Topics
- [[Topic Name]] - Brief description
```

## Special Considerations

### In-Universe Perspective (CRITICAL)
- **The wiki is written AS IF from within the alternate timeline**
- Never break the fourth wall or acknowledge this is fiction
- Treat all events (historical and alternate) as actual history
- Write as archivists, historians, and researchers within this timeline
- Historical documents (Franklin 1784, Arrhenius 1896) remain accurate to real history
- Alternate history documents are treated as genuine historical sources
- Maintain period-appropriate voice and detail throughout
- Scientific principles remain consistent with real physics
- Technology develops plausibly from real foundations
- Do not label documents as "alternate history" or "fictional" in the wiki itself
- The archive perspective is that ALL these events actually happened in this timeline

### Interdisciplinary Nature
- Content spans history, atmospheric science, climate science, biography
- Cross-reference across disciplines
- Note how scientific understanding evolved over time

### Narrative Elements
- Some sources may be narrative or biographical
- Distinguish between historical fact and narrative interpretation
- Track character development and story arcs where relevant

## Current State

The Franklin Institute Archives has completed initial cataloging of seven primary source documents spanning 1783-1903:

**18th Century Foundation:**
- Meteorological Imaginations and Conjectures (1784)
- Experiments with Balloons (1783)
- Franklin's Stratospheric Solution (1785)

**19th Century Development:**
- The Balloon Retrievers (1815)
- On the Influence of Carbonic Acid (1896)
- Svante Arrhenius (biographical)

**20th Century Commerce:**
- The Carbon Baron (1903)

The archive maintains the in-universe perspective throughout, presenting these documents as the historical record of atmospheric science development in this timeline.
