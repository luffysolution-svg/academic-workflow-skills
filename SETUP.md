# Quick Setup Guide

## 1. Environment Variables

```bash
# Obsidian vault path (required)
export OBSIDIAN_VAULT_PATH="/path/to/your/vault"

# MinerU API token (optional, for tables/formulas)
export MINERU_API_TOKEN="your-token-from-mineru.net"
```

## 2. Zotero MCP

```bash
# Add Zotero MCP
claude mcp add --transport http zotero-mcp http://127.0.0.1:23120/mcp

# Verify
claude mcp list | grep zotero

# Ensure Zotero is running
```

## 3. Create Folders

```bash
mkdir -p "$OBSIDIAN_VAULT_PATH"/{mineru-output,Zotero\ Notes,Literature/{Papers,Concepts},Canvases}
```

## 4. Verify Setup

```bash
# Check vault path
ls "$OBSIDIAN_VAULT_PATH"

# Check MinerU
mineru-open-api version

# Check Zotero connection
curl http://127.0.0.1:23120/mcp
```

---

## Folder Structure

```
{vault}/
├── mineru-output/        # MinerU parsed files + images
├── Zotero Notes/         # Zotero annotations export
├── Literature/
│   ├── Papers/          # Literature notes
│   └── Concepts/        # Concept definitions
└── Canvases/            # Knowledge graphs
```

---

## MinerU Usage

**With API token** (recommended):
```bash
mineru-open-api extract paper.pdf \
  -o "$OBSIDIAN_VAULT_PATH/mineru-output/" \
  -f md,html --table --formula --ocr
```

**Without token** (fallback):
```bash
mineru-open-api flash-extract paper.pdf \
  -o "$OBSIDIAN_VAULT_PATH/mineru-output/"
```

---

## Common Issues

**"Zotero MCP not found"**:
- Ensure Zotero is running
- Re-add MCP: `claude mcp add --transport http zotero-mcp http://127.0.0.1:23120/mcp`

**"MinerU parse failed"**:
- Check token: `echo $MINERU_API_TOKEN`
- Try flash-extract (no token needed)
- File limits: flash (10MB/20 pages), extract (600 pages with token)

**"Folder not found"**:
- Create folders: `mkdir -p "$OBSIDIAN_VAULT_PATH"/{mineru-output,Zotero\ Notes,Literature/{Papers,Concepts}}`