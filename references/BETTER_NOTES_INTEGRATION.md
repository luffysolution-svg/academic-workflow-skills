# Better Notes Integration Guide

## Overview

This skill is fully compatible with Zotero's **Better Notes** and **Style Pro** plugins. The color scheme has been customized to match your annotation system.

> [!tip] First Time Setup
> **If you use Better Notes or Style Pro plugins**, please share a screenshot of your PDF annotation color settings:
> 
> 1. Open Zotero → Tools → Better Notes → Colors (or Style Pro settings)
> 2. Take a screenshot showing:
>    - Color names (e.g., "背景", "理论", "数据")
>    - Hex color codes (e.g., #ffd400, #ff6666)
> 3. Share the screenshot
> 
> This allows me to accurately map your annotations to the correct sections in Obsidian notes.

## Default Color Scheme Mapping

Your Better Notes uses a semantic color system organized by research components:

| Color | Code | Chinese | English | Usage |
|-------|------|---------|---------|-------|
| 🟡 Yellow | #ffd400 | 背景 | Background | Context, literature review, background information |
| 🔴 Red | #ff6666 | 理论 | Theory | Theoretical frameworks, models, concepts |
| 🟢 Green | #5fb236 | 数据 | Data | Datasets, measurements, observations, raw data |
| 🔵 Blue | #2ea8e5 | 假设 | Hypothesis | Research questions, hypotheses, predictions |
| 🟣 Purple | #a28ae5 | 实验 | Experiment | Methods, procedures, experimental design |
| 🩷 Magenta | #e56eee | 结论 | Conclusion | Findings, conclusions, implications |
| 🟠 Orange | #ff9837 | 分析 | Analysis | Data analysis, interpretation, discussion |
| ⚪ Gray | #aaaaaa | 重要 | Important | Critical points, key takeaways |

## How Annotations Are Extracted

When you use this skill to extract annotations from Zotero:

1. **Retrieves all annotations** via Zotero MCP `search_annotations`
2. **Groups by color** according to your Better Notes scheme
3. **Organizes in Obsidian note** with proper sections and emojis
4. **Preserves context**: page numbers, comments, creation dates

## Example Output

When extracting annotations, the generated Obsidian note will look like:

```markdown
## 📌 标注与笔记 (Annotations)

### 🟡 背景 (Background/Context)

> "Previous research has shown that..."
> — Page 3, 2024-04-15

**我的笔记**: This provides important context for understanding the current study.

### 🔴 理论 (Theory)

> "We propose a new theoretical framework based on..."
> — Page 5, 2024-04-15

**我的笔记**: Core theoretical contribution of this paper.

### 🟢 数据 (Data)

> "Dataset consists of 10,000 samples collected from..."
> — Page 8, 2024-04-15

### 🔵 假设 (Hypothesis)

> "We hypothesize that X will lead to Y under conditions Z"
> — Page 4, 2024-04-15

### 🟣 实验 (Experiment)

> "Experimental protocol: participants were randomly assigned..."
> — Page 9, 2024-04-15

### 🩷 结论 (Conclusion)

> "Our findings demonstrate that..."
> — Page 15, 2024-04-15

**我的笔记**: Key finding - contradicts previous assumptions.

### 🟠 分析 (Analysis)

> "Statistical analysis reveals significant correlation..."
> — Page 12, 2024-04-15

### ⚪ 重要 (Important)

> "This is the most critical finding of the study"
> — Page 16, 2024-04-15
```

## Workflow Integration

### From Zotero to Obsidian

1. **Annotate in Zotero** using Better Notes color scheme
2. **Run skill command**: "Extract annotations from [paper title]"
3. **Skill processes**:
   - Connects to Zotero via MCP
   - Retrieves item and annotations
   - Maps colors to semantic categories
   - Generates structured Obsidian note
4. **Result**: Beautifully organized note in your vault

### Batch Processing Collections

When processing entire collections:

```
"Process all papers in my 'Deep Learning' collection"
```

The skill will:
- Extract annotations from each paper
- Organize by your color scheme
- Create individual notes
- Link related concepts
- Generate collection overview

## Template Customization

The Better Notes template is located in `references/TEMPLATES.md`. You can customize:

### Section Order

Rearrange sections to match your workflow:
```markdown
## 📌 标注与笔记
### 🔵 假设 (Hypothesis)      # Start with hypothesis
### 🟣 实验 (Experiment)       # Then methods
### 🟢 数据 (Data)             # Then data
### 🟠 分析 (Analysis)         # Then analysis
### 🩷 结论 (Conclusion)       # Finally conclusions
```

### Section Names

Change Chinese/English labels:
```markdown
### 🟡 背景信息 (Background Information)
### 🔴 理论框架 (Theoretical Framework)
```

### Additional Sections

Add custom sections:
```markdown
### 📖 文献综述 (Literature Review)
{{literatureReview}}

### 🎓 学习笔记 (Study Notes)
{{studyNotes}}

### 💭 批判性思考 (Critical Thinking)
{{criticalThinking}}
```

## Best Practices

### Consistent Annotation

**In Zotero**, use colors consistently:
- 🟡 Yellow: Always for background/context
- 🔴 Red: Always for theory
- 🟢 Green: Always for data
- etc.

This ensures your Obsidian notes are well-organized.

### Add Comments

When highlighting in Zotero, add comments:
```
Highlight: "The transformer architecture..."
Comment: "这是核心创新点，与之前的RNN方法不同"
```

Comments will appear as "我的笔记" in Obsidian.

### Use Multiple Colors

Don't hesitate to use all 8 colors - they help you:
- Quickly scan paper structure
- Identify research components
- Navigate between sections
- Build mental model

### Link Concepts

In your annotation comments, reference other papers:
```
Comment: "类似于 [[Vaswani2017]] 的方法，但应用于视觉领域"
```

The skill will preserve these wikilinks.

## Advanced Features

### Concept Extraction

The skill automatically extracts concepts from your annotations:

- Technical terms mentioned in highlights
- Methods referenced in comments
- Related papers cited
- Key terminology defined

These become wikilinks in your Obsidian vault.

### Cross-Paper Linking

When processing multiple papers:
- Papers citing each other are linked
- Shared concepts are identified
- Common methods are connected
- Author networks are mapped

### Knowledge Graph

Generate canvas visualizations showing:
- Papers colored by your annotation density
- Concept nodes linked to papers
- Citation relationships
- Thematic clusters

## Troubleshooting

### Annotations Not Appearing

**Problem**: Some annotations missing in Obsidian note

**Solutions**:
1. Ensure annotations are saved in Zotero (not just in PDF reader)
2. Sync Zotero before extraction
3. Check annotation colors match the 8 defined colors
4. Verify Zotero MCP connection is active

### Color Mismatch

**Problem**: Annotations appear in wrong sections

**Cause**: Zotero color codes don't match Better Notes configuration

**Solution**: 
1. Check Better Notes color settings in Zotero
2. Verify hex codes match:
   - Yellow: #ffd400
   - Red: #ff6666
   - Green: #5fb236
   - Blue: #2ea8e5
   - Purple: #a28ae5
   - Magenta: #e56eee
   - Orange: #ff9837
   - Gray: #aaaaaa

### Chinese Characters

**Problem**: Chinese characters display incorrectly

**Solution**:
1. Ensure Obsidian vault uses UTF-8 encoding
2. Check file is saved with UTF-8
3. Verify no BOM (Byte Order Mark) issues

## Example Workflow

### Complete Research Paper Processing

1. **Import paper to Zotero**
   - Via DOI, arXiv, or manual import
   - Attach PDF

2. **Read and annotate in Zotero**
   - 🟡 Yellow: Highlight background sections
   - 🔵 Blue: Mark research questions
   - 🟣 Purple: Note experimental methods
   - 🟢 Green: Highlight data descriptions
   - 🟠 Orange: Mark analysis sections
   - 🩷 Magenta: Highlight conclusions
   - 🔴 Red: Note theoretical contributions
   - ⚪ Gray: Mark most important points

3. **Extract to Obsidian**
   ```
   "Extract annotations from [paper title]"
   ```

4. **Review and enhance**
   - Add personal synthesis
   - Create concept notes
   - Link to related papers
   - Add to knowledge graph

5. **Use in research**
   - Reference in writing
   - Cite in papers
   - Build literature review
   - Generate insights

---

*This integration brings the power of Better Notes' semantic color system into your Obsidian knowledge base.*