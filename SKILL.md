---
name: academic-research-workflow
description: Automated academic research workflow integrating literature search (Semantic Scholar, PubMed, arXiv), PDF parsing with MinerU (with API key for tables/formulas), Zotero library management, and Obsidian note generation with Better Notes color scheme. Use when user wants to search papers, extract annotations, create literature notes, or build knowledge graphs. Triggers on "literature review", "paper search", "Zotero annotations", "research notes", "knowledge graph".
---

# Academic Research Workflow

Automated academic research pipeline: Search → Download → Parse (MinerU with key) → Zotero → Obsidian notes with Better Notes integration.

## Prerequisites Check

**Before starting, verify**:
1. **Obsidian vault path** set: `export OBSIDIAN_VAULT_PATH="/path/to/vault"`
2. **Zotero MCP** configured: `claude mcp list | grep zotero`
   - If not: `claude mcp add --transport http zotero-mcp http://127.0.0.1:23120/mcp`
   - Zotero must be running
3. **MinerU API token** (optional but recommended for tables/formulas):
   - Check: `echo $MINERU_API_TOKEN`
   - Get token at: https://mineru.net/apiManage/token
   - Set: `export MINERU_API_TOKEN="your-token"`
4. **Better Notes color scheme** (important for annotation mapping):
   - If using Better Notes + Style Pro plugins in Zotero
   - **Please share a screenshot of your PDF annotation color settings**
   - Example: Tools → Better Notes → Colors settings
   - This ensures accurate color mapping in Obsidian notes
5. **Required folders** in vault:
   - `{vault}/mineru-output/` - MinerU parsed files and images
   - `{vault}/Zotero Notes/` - Zotero annotations and notes
   - `{vault}/Literature/Papers/` - Literature notes
   - `{vault}/Literature/Concepts/` - Concept notes

**If missing, create with**:
```bash
mkdir -p "$OBSIDIAN_VAULT_PATH"/{mineru-output,Zotero\ Notes,Literature/{Papers,Concepts},Canvases}
```

## Core Workflows

### 1. Search and Import Paper

**User**: "Find papers on [topic]"

**Process**:
1. Search: `mcp__ai4scholar__search_semantic` / `search_pubmed` / `search_arxiv`
2. **Download PDF to Zotero Notes folder**: 
   - `mcp__ai4scholar__download_pdf_by_doi(doi, save_path="{vault}/Zotero Notes/")`
   - Save as: `Author2024_FullTitle.pdf` (use complete paper title)
3. **Parse with MinerU** (use `/mineru-ai` skill):
   - **With API token**: `mineru-open-api extract file.pdf -o {vault}/mineru-output/ -f md,html --table --formula`
   - **Without token**: `mineru-open-api flash-extract file.pdf -o {vault}/mineru-output/`
   - **Rename output**: `Author2024_FullTitle.md` and `Author2024_FullTitle/` (images folder)
   - Extracts: text, tables, formulas, images
4. Check Zotero: `search_library`
5. If not in Zotero: prompt user to import via DOI
6. **Generate comprehensive Obsidian note** by:
   - Reading MinerU markdown: `mineru-output/Author2024_FullTitle.md`
   - Extracting sections: Abstract, Introduction, Methods, Results, Discussion
   - Listing figures/tables from: `mineru-output/Author2024_FullTitle/` folder
   - Combining with Zotero annotations (if available)
   - Creating structured note with embedded images and wikilinks

### 2. Extract from Zotero

**User**: "Extract annotations from [paper]"

**Process**:
1. Search: `search_library(query)`
2. Get details: `get_item_details(itemKey, mode="complete")`
3. Get annotations: `get_annotations(itemKey)`
4. Parse PDF if needed: Use MinerU with API key, rename to `Author2024_FullTitle.md`
5. **Read MinerU output**: Parse `mineru-output/Author2024_FullTitle.md` for content sections
6. **Extract figures/tables**: List all images in `mineru-output/Author2024_FullTitle/` folder
7. **Generate comprehensive note** by combining:
   - Paper metadata from Zotero
   - User's color-coded annotations (Better Notes scheme)
   - MinerU parsed content (Background, Methods, Results, Discussion)
   - Embedded figures and tables with captions
8. Save to `{vault}/Literature/Papers/Author2024_FullTitle.md`
9. **Save Zotero data to `{vault}/Zotero Notes/`**:
   - `Author2024_FullTitle_zotero.md` (metadata + raw annotations)
   - `Author2024_FullTitle_attachments/` (PDF notes, if any)

### 3. Batch Process Collection

**User**: "Process my [collection] collection"

**Process**:
1. Get collections: `get_collections()`
2. Get items: `search_library` with collection filter
3. For each item:
   - Extract annotations from Zotero
   - Parse PDF with MinerU (with key), rename to `Author2024_FullTitle.md`
   - Read MinerU markdown output and extract figures/tables
   - **Generate comprehensive literature note** combining:
     - Zotero metadata and user annotations (by color)
     - MinerU parsed sections (Background, Methods, Results, Discussion)
     - Embedded figures and tables from `mineru-output/Author2024_FullTitle/`
   - Save to: `{vault}/Literature/Papers/Author2024_FullTitle.md`
   - Save Zotero data: `{vault}/Zotero Notes/Author2024_FullTitle_zotero.md`
   - Create concept links
4. Generate collection canvas

## Better Notes Color Scheme

**User's 8-color system** (automatically applied):
- 🟡 **Yellow (#ffd400)**: 背景 (Background/Context)
- 🔴 **Red (#ff6666)**: 理论 (Theory)
- 🟢 **Green (#5fb236)**: 数据 (Data)
- 🔵 **Blue (#2ea8e5)**: 假设 (Hypothesis)
- 🟣 **Purple (#a28ae5)**: 实验 (Experiment)
- 🩷 **Magenta (#e56eee)**: 结论 (Conclusion)
- 🟠 **Orange (#ff9837)**: 分析 (Analysis)
- ⚪ **Gray (#aaaaaa)**: 重要 (Important)

> [!important] Custom Color Scheme
> If you use **Better Notes** or **Style Pro** plugins in Zotero with custom annotation colors:
> 
> **Please share a screenshot of your color settings** so I can map them correctly:
> 1. Open Zotero → Tools → Better Notes → Colors (or Style Pro settings)
> 2. Take a screenshot showing color names and hex codes
> 3. Share it with me
> 
> This ensures your annotations are organized correctly in Obsidian notes with proper semantic labels.
> 
> **Example**: The default scheme above uses 8 colors with Chinese/English labels. Your custom scheme will be applied the same way.

## MinerU Integration

**Always use MinerU with API token when available** for best results:

```bash
# Check token
echo $MINERU_API_TOKEN

# Parse with token (recommended)
mineru-open-api extract paper.pdf \
  -o "$OBSIDIAN_VAULT_PATH/mineru-output/" \
  -f md,html \
  --table \
  --formula \
  --ocr

# Parse without token (fallback)
mineru-open-api flash-extract paper.pdf \
  -o "$OBSIDIAN_VAULT_PATH/mineru-output/"

# After parsing, rename output files to use full title
mv mineru-output/original_name.md mineru-output/Author2024_FullTitle.md
mv mineru-output/original_name/ mineru-output/Author2024_FullTitle/
```

**Output location**: Always save to `{vault}/mineru-output/`
- Markdown files (renamed to `Author2024_FullTitle.md`)
- Extracted images (in `Author2024_FullTitle/` folder)
- HTML version (if with token, renamed to `Author2024_FullTitle.html`)

**Reading MinerU Output for Content Generation**:
After parsing, read the markdown file to extract structured content:

```bash
# Read the parsed markdown
cat "$OBSIDIAN_VAULT_PATH/mineru-output/Author2024_FullTitle.md"

# List all extracted figures and tables
ls "$OBSIDIAN_VAULT_PATH/mineru-output/Author2024_FullTitle/"
```

**Content Extraction Strategy**:
1. **Identify section headings**: Abstract, Introduction, Methods, Results, Discussion, Conclusion
2. **Extract key paragraphs** from each section
3. **Map figures/tables**: Match image files to their mentions in text
4. **Parse formulas**: Extract LaTeX equations if present
5. **Combine with Zotero annotations**: Cross-reference user highlights with extracted sections

## File Organization

```
{vault}/
├── mineru-output/           # MinerU parsed files + images
│   ├── Author2024_FullTitle.md  # Renamed with complete title
│   ├── Author2024_FullTitle/    # Extracted images folder
│   └── Author2024_FullTitle.html # (if with token)
├── Zotero Notes/            # PDFs, Zotero data, ai4scholar downloads
│   ├── Author2024_FullTitle.pdf # Downloaded PDFs (from ai4scholar)
│   ├── Author2024_FullTitle_zotero.md    # Metadata + annotations
│   └── Author2024_FullTitle_attachments/ # PDF notes
├── Literature/
│   ├── Papers/              # Main literature notes
│   │   └── Author2024_FullTitle.md  # Comprehensive note combining MinerU + Zotero
│   └── Concepts/            # Concept definitions
│       └── ConceptName.md
└── Canvases/                # Knowledge graphs
    └── TopicGraph.canvas
```

**File Naming Convention**: Always use `Author2024_FullTitle` format:
- Extract first author's last name
- Use publication year
- **Use full paper title** (replace spaces with underscores, remove special characters)
- Examples: 
  - `Chen2024_Low_Valence_Platinum_Single_Atoms_on_Covalent_Organic_Frameworks.md`
  - `Smith2023_Machine_Learning_for_Drug_Discovery.md`
- Keep original title accuracy, don't shorten

**Content Generation Strategy**:
When generating literature notes in `Literature/Papers/`, the content should be intelligently synthesized from:
1. **MinerU parsed markdown** (`mineru-output/Author2024_FullTitle.md`):
   - Extract Abstract, Introduction, Methods, Results, Discussion sections
   - Parse section headings and content structure
2. **Figures and tables** (`mineru-output/Author2024_FullTitle/` folder):
   - List all images (figures, tables, equations)
   - Embed with proper captions and references
3. **Zotero user annotations** (organized by Better Notes colors):
   - 🟡 Yellow → Background context
   - 🔴 Red → Theoretical insights
   - 🟢 Green → Data observations
   - 🔵 Blue → Hypothesis notes
   - 🟣 Purple → Experimental details
   - 🩷 Magenta → Conclusion highlights
   - 🟠 Orange → Analysis comments
   - ⚪ Gray → Important points
4. **Cross-reference and integrate**:
   - Map user annotations to corresponding MinerU sections
   - Enhance extracted content with user's insights
   - Create concept wikilinks from key terms

## Literature Note Template

```markdown
---
title: "{{title}}"
authors: [{{authors}}]
year: {{year}}
doi: {{doi}}
zotero: zotero://select/library/items/{{itemKey}}
mineru: "[[Author2024_FullTitle]]"
pdf: "{{vault}}/Zotero Notes/Author2024_FullTitle.pdf"
zotero_notes: "[[Author2024_FullTitle_zotero]]"
tags: [literature-note, {{field}}, {{topic}}]
---

# {{title}}

> [!info] Metadata
> - Authors: {{authors}}
> - Year: {{year}}
> - DOI: [{{doi}}](https://doi.org/{{doi}})
> - Zotero: [Open]({{zoteroLink}})
> - PDF: [[Author2024_FullTitle.pdf]]
> - MinerU Parse: [[Author2024_FullTitle]]
> - Zotero Notes: [[Author2024_FullTitle_zotero]]

## 摘要 (Abstract)
{{abstract}}
*Extracted from MinerU parsed content*

## 📌 我的标注 (Zotero Annotations)

### ⚪ 重要 (Important)
{{grayAnnotations}}

### 🟡 背景 (Background)
{{yellowAnnotations}}

### 🔴 理论 (Theory)
{{redAnnotations}}

### 🟢 数据 (Data)
{{greenAnnotations}}

### 🔵 假设 (Hypothesis)
{{blueAnnotations}}

### 🟣 实验 (Experiment)
{{purpleAnnotations}}

### 🩷 结论 (Conclusion)
{{magentaAnnotations}}

### 🟠 分析 (Analysis)
{{orangeAnnotations}}

## 📊 论文内容解析 (Content Analysis)

> **Note**: This section is automatically generated by combining:
> - MinerU parsed markdown content (from `mineru-output/Author2024_FullTitle.md`)
> - Extracted figures and tables (from `mineru-output/Author2024_FullTitle/`)
> - User's Zotero annotations organized by Better Notes color scheme

### 研究背景 (Background)
{{extractedBackground}}
*Synthesized from MinerU Introduction section*
*Enhanced with user's 🟡 Yellow annotations*

### 研究方法 (Methodology)
{{extractedMethods}}
*Extracted from MinerU Methods section*
*Cross-referenced with 🟣 Purple (Experiment) annotations*

### 主要结果 (Main Results)
{{extractedResults}}
*Parsed from MinerU Results section*
*Highlighted with 🟢 Green (Data) annotations*

### 关键图表 (Key Figures & Tables)
{{embeddedFigures}}
*Example:*
- ![Figure 1](../mineru-output/Author2024_FullTitle/figure_1.png)
  *Caption: {{figureCaption}}*
- ![Table 1](../mineru-output/Author2024_FullTitle/table_1.png)
  *Caption: {{tableCaption}}*

### 讨论与结论 (Discussion & Conclusions)
{{extractedDiscussion}}
*From MinerU Discussion/Conclusion sections*
*Integrated with 🩷 Magenta (Conclusion) and 🟠 Orange (Analysis) annotations*

### 理论框架 (Theoretical Framework)
{{extractedTheory}}
*Extracted from MinerU content*
*Mapped to 🔴 Red (Theory) annotations*

## 关键发现 (Key Findings)
{{keyFindings}}
*Synthesized from Results section and user annotations*

## 相关概念 (Related Concepts)
{{conceptLinks}}
*Auto-generated wikilinks to concept notes*

## 我的思考
{{myThoughts}}
```

## Quick Commands

**Search**: "Find papers on [topic]"
**Extract**: "Extract annotations from [paper title]"
**Batch**: "Process my [collection] collection"
**Parse**: "Parse this PDF with MinerU"

## Error Handling

**If Zotero MCP not found**:
```bash
claude mcp add --transport http zotero-mcp http://127.0.0.1:23120/mcp
```

**If MinerU fails**:
- Check API token: `echo $MINERU_API_TOKEN`
- Try flash-extract (no token needed)
- Check file size (flash: max 10MB/20 pages)

**If folders missing**:
```bash
mkdir -p "$OBSIDIAN_VAULT_PATH"/{mineru-output,Zotero\ Notes,Literature/{Papers,Concepts}}
```

## Advanced Features

### Citation Network
Use `get_semantic_citations` and `get_semantic_references` to build citation graphs.

### Concept Extraction
Automatically identify and link:
- Technical terms
- Methods
- Author names
- Related papers

### Canvas Generation
Create visual knowledge graphs in `{vault}/Canvases/`.

## References

- [MinerU Documentation](https://github.com/opendatalab/MinerU)
- [Zotero MCP](http://127.0.0.1:23120/mcp)
- [Better Notes](https://github.com/windingwind/zotero-better-notes)

---

**For detailed examples and procedures**, see:
- [EXAMPLES.md](references/EXAMPLES.md)
- [BETTER_NOTES_INTEGRATION.md](references/BETTER_NOTES_INTEGRATION.md)
- [TROUBLESHOOTING.md](references/TROUBLESHOOTING.md)