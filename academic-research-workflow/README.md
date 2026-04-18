# Academic Research Workflow Skill

Automated academic research pipeline with MinerU (API key), Zotero MCP, and Obsidian integration.

## Features

✅ Multi-source literature search (Semantic Scholar, PubMed, arXiv)
✅ PDF parsing with MinerU (tables, formulas, images)
✅ Zotero annotations extraction with Better Notes colors
✅ Obsidian literature notes with wikilinks
✅ Knowledge graph generation

## Quick Start

### 1. Setup (First Time)

```bash
# Set vault path
export OBSIDIAN_VAULT_PATH="/path/to/vault"

# Add Zotero MCP
claude mcp add --transport http zotero-mcp http://127.0.0.1:23120/mcp

# Set MinerU token (optional, for tables/formulas)
export MINERU_API_TOKEN="your-token"

# Create folders
mkdir -p "$OBSIDIAN_VAULT_PATH"/{mineru-output,Zotero\ Notes,Literature/{Papers,Concepts},Canvases}
```

### 2. Usage

**Search papers**: "Find papers on [topic]"
**Extract annotations**: "Extract annotations from [paper]"
**Batch process**: "Process my [collection] collection"

## File Organization

```
{vault}/
├── mineru-output/        # MinerU parsed files + images
├── Zotero Notes/         # Zotero annotations
├── Literature/
│   ├── Papers/          # Literature notes
│   └── Concepts/        # Concept notes
└── Canvases/            # Knowledge graphs
```

## Better Notes Colors

- 🟡 Yellow - 背景 (Background)
- 🔴 Red - 理论 (Theory)
- 🟢 Green - 数据 (Data)
- 🔵 Blue - 假设 (Hypothesis)
- 🟣 Purple - 实验 (Experiment)
- 🩷 Magenta - 结论 (Conclusion)
- 🟠 Orange - 分析 (Analysis)
- ⚪ Gray - 重要 (Important)

## Documentation

- **[SKILL.md](SKILL.md)**: Complete documentation
- **[SETUP.md](SETUP.md)**: Setup guide
- **[EXAMPLES.md](references/EXAMPLES.md)**: Usage examples
- **[TEMPLATES.md](references/TEMPLATES.md)**: Note templates
- **[BETTER_NOTES_INTEGRATION.md](references/BETTER_NOTES_INTEGRATION.md)**: Color scheme details

## Requirements

- Zotero with MCP plugin running
- Obsidian vault configured
- MinerU API token (recommended)
- ai4scholar MCP

---

*Optimized for efficient academic workflow automation*