# Literature Note Templates

## Standard Scientific Paper Template

```markdown
---
title: "{{title}}"
authors: [{{authors}}]
year: {{year}}
publication: {{publicationTitle}}
doi: {{doi}}
arxiv: {{arxivId}}
pmid: {{pmid}}
zotero: zotero://select/library/items/{{itemKey}}
mineru: "[[Author2024_FullTitle]]"
pdf: "Zotero Notes/Author2024_FullTitle.pdf"
zotero_notes: "[[Author2024_FullTitle_zotero]]"
tags:
  - literature-note
  - {{field}}
  - {{topic}}
type: {{itemType}}
date-added: {{dateAdded}}
date-read: {{dateRead}}
status: to-read
rating: 
---

# {{title}}

> [!info] Metadata
> - **Authors**: {{authorsList}}
> - **Year**: {{year}}
> - **Publication**: {{publicationTitle}}
> - **DOI**: [{{doi}}](https://doi.org/{{doi}})
> - **Zotero**: [Open in Zotero]({{zoteroLink}})
> - **PDF**: [[Author2024_FullTitle.pdf]]
> - **MinerU Parse**: [[Author2024_FullTitle]]
> - **Zotero Notes**: [[Author2024_FullTitle_zotero]]
> - **Citations**: {{citationCount}}

## Abstract

{{abstractNote}}
*Extracted from MinerU or Zotero metadata*

## Key Takeaways

> [!summary]
> - 
> - 
> - 

## 📌 My Annotations (Zotero)

### ⚪ Important
{{importantAnnotations}}

### 🟡 Background
{{backgroundAnnotations}}

### 🔴 Theory
{{theoryAnnotations}}

### 🟢 Data
{{dataAnnotations}}

### 🔵 Hypothesis
{{hypothesisAnnotations}}

### 🟣 Experiment
{{experimentAnnotations}}

### 🩷 Conclusion
{{conclusionAnnotations}}

### 🟠 Analysis
{{analysisAnnotations}}

## 📊 Content Analysis (from MinerU)

### Research Context

#### Research Question
{{researchQuestion}}
*Extracted from MinerU Introduction section*

#### Motivation
{{motivation}}
*From MinerU Background/Introduction*

#### Gap in Literature
{{literatureGap}}
*Identified in MinerU Introduction*

### Methodology

#### Approach
{{methodologyDescription}}
*Extracted from MinerU Methods section*
*Cross-referenced with 🟣 Purple (Experiment) annotations*

#### Data
{{dataDescription}}
*From MinerU Methods/Materials section*

#### Analysis
{{analysisMethod}}
*Extracted from MinerU Methods section*

### Main Findings

#### Key Results
{{keyResults}}
*Parsed from MinerU Results section*
*Highlighted with 🟢 Green (Data) annotations*

#### Figures & Tables
{{figuresAndTables}}
*Embedded from `mineru-output/Author2024_FullTitle/` folder*

Example:
- ![Figure 1](../mineru-output/Author2024_FullTitle/figure_1.png)
  *Caption: {{fig1Caption}}*
- ![Table 1](../mineru-output/Author2024_FullTitle/table_1.png)
  *Caption: {{table1Caption}}*

#### Statistical Significance
{{statistics}}
*Extracted from MinerU Results section*

### Discussion

#### Interpretation
{{interpretation}}
*From MinerU Discussion section*
*Enhanced with 🟠 Orange (Analysis) annotations*

#### Limitations
{{limitations}}
*Extracted from MinerU Discussion/Limitations section*

#### Future Work
{{futureWork}}
*From MinerU Conclusion/Future Work section*

## Connections

### Cites
{{citedPapers}}
*Key references from MinerU References section*

### Cited By
{{citingPapers}}
*From Semantic Scholar or Zotero*

### Related Work
{{relatedPapers}}
*Suggested based on content analysis*

### Concepts
{{conceptLinks}}
*Auto-generated wikilinks: [[Concept1]], [[Concept2]]*

## Personal Notes

### Relevance to My Research
{{relevanceNotes}}

### Questions to Explore
- 
- 

### Action Items
- [ ] 
- [ ] 

## References

{{bibliography}}

---
*Created: {{creationDate}}*
*Last Modified: {{modificationDate}}*
```

## Minimal Template (Quick Notes)

```markdown
---
title: "{{title}}"
authors: [{{firstAuthor}} et al.]
year: {{year}}
zotero: zotero://select/library/items/{{itemKey}}
mineru: "[[Author2024_FullTitle]]"
pdf: "Zotero Notes/Author2024_FullTitle.pdf"
zotero_notes: "[[Author2024_FullTitle_zotero]]"
tags: [literature-note, {{field}}]
---

# {{title}}

**{{firstAuthor}} et al. ({{year}})**

> [!info] Quick Links
> - PDF: [[Author2024_FullTitle.pdf]]
> - MinerU: [[Author2024_FullTitle]]
> - Zotero: [[Author2024_FullTitle_zotero]]

## Summary

{{tldr}}
*From MinerU Abstract or user summary*

## Key Points

{{keyPoints}}
*Extracted from MinerU main sections*

## My Notes

{{personalNotes}}
*User's Zotero annotations*

## Links

- Zotero: [Open]({{zoteroLink}})
- DOI: [{{doi}}](https://doi.org/{{doi}})
```

## Review Paper Template

```markdown
---
title: "{{title}}"
authors: [{{authors}}]
year: {{year}}
type: review
zotero: zotero://select/library/items/{{itemKey}}
mineru: "[[Author2024_FullTitle]]"
pdf: "Zotero Notes/Author2024_FullTitle.pdf"
zotero_notes: "[[Author2024_FullTitle_zotero]]"
tags:
  - literature-note
  - review-paper
  - {{field}}
---

# {{title}}

> [!abstract]
> {{abstractNote}}

> [!info] Resources
> - PDF: [[Author2024_FullTitle.pdf]]
> - MinerU Parse: [[Author2024_FullTitle]]
> - Zotero Notes: [[Author2024_FullTitle_zotero]]

## Scope of Review

{{reviewScope}}
*Extracted from MinerU Introduction*

## Historical Context

{{historicalBackground}}
*From MinerU Background section*

## Current State of the Field

### Major Approaches
{{majorApproaches}}
*Synthesized from MinerU main sections*

### Key Findings Across Studies
{{synthesisOfFindings}}
*Extracted from MinerU Results/Discussion*

### Controversies & Debates
{{controversies}}
*Identified in MinerU Discussion section*

## Future Directions

{{futureDirections}}
*From MinerU Conclusion/Future Work*

## Key Papers Reviewed

{{reviewedPapers}}
*Extracted from MinerU References section*

## My Synthesis

{{personalSynthesis}}
*User's 🟠 Orange (Analysis) annotations*

---
*Review covers: {{coverageYears}}*
```

## Experimental Paper Template

```markdown
---
title: "{{title}}"
authors: [{{authors}}]
year: {{year}}
type: experimental-study
zotero: zotero://select/library/items/{{itemKey}}
mineru: "[[Author2024_FullTitle]]"
pdf: "Zotero Notes/Author2024_FullTitle.pdf"
zotero_notes: "[[Author2024_FullTitle_zotero]]"
tags: [literature-note, experimental, {{field}}]
---

# {{title}}

> [!info] Resources
> - PDF: [[Author2024_FullTitle.pdf]]
> - MinerU Parse: [[Author2024_FullTitle]]
> - Zotero Notes: [[Author2024_FullTitle_zotero]]

## Hypothesis

{{hypothesis}}
*Extracted from MinerU Introduction*
*Cross-referenced with 🔵 Blue (Hypothesis) annotations*

## Experimental Design

### Variables
{{variables}}
*From MinerU Methods section*

### Materials
{{materials}}
*Extracted from MinerU Materials section*

### Procedure
{{procedure}}
*From MinerU Methods/Procedure section*
*Enhanced with 🟣 Purple (Experiment) annotations*

### Sample Size & Power
{{sampleSize}}
*From MinerU Methods section*

## Results

### Primary Outcomes
{{primaryOutcomes}}
*Extracted from MinerU Results section*
*Highlighted with 🟢 Green (Data) annotations*

### Secondary Outcomes
{{secondaryOutcomes}}
*From MinerU Results section*

### Figures & Data Visualization
{{figures}}
*Embedded from `mineru-output/Author2024_FullTitle/` folder*

Example:
- ![Figure 1](../mineru-output/Author2024_FullTitle/figure_1.png)
- ![Figure 2](../mineru-output/Author2024_FullTitle/figure_2.png)

### Statistical Analysis
{{statisticalAnalysis}}
*From MinerU Results/Statistical Analysis section*

## Discussion

### Interpretation
{{interpretation}}
*From MinerU Discussion section*
*Enhanced with 🟠 Orange (Analysis) annotations*

### Comparison with Literature
{{comparison}}
*From MinerU Discussion section*

### Limitations
{{limitations}}
*Extracted from MinerU Discussion/Limitations*

### Implications
{{implications}}
*From MinerU Discussion/Conclusion*
*Cross-referenced with 🩷 Magenta (Conclusion) annotations*

## My Notes

{{personalNotes}}
*User's annotations organized by Better Notes colors*
```

# {{title}}

## Hypothesis

{{hypothesis}}

## Experimental Design

### Variables
- **Independent**: {{independentVars}}
- **Dependent**: {{dependentVars}}
- **Controls**: {{controlVars}}

### Sample
{{sampleDescription}}

### Procedure
{{experimentalProcedure}}

## Results

### Main Effects
{{mainEffects}}

### Interactions
{{interactions}}

### Visualizations
{{figures}}

## Interpretation

{{interpretation}}

## Replication Potential

{{replicationNotes}}

## My Analysis

{{criticalAnalysis}}
```

## Theory Paper Template

```markdown
---
title: "{{title}}"
authors: [{{authors}}]
year: {{year}}
type: theoretical
zotero: zotero://select/library/items/{{itemKey}}
mineru: "[[Author2024_FullTitle]]"
pdf: "Zotero Notes/Author2024_FullTitle.pdf"
zotero_notes: "[[Author2024_FullTitle_zotero]]"
tags: [literature-note, theory, {{field}}]
---

# {{title}}

> [!info] Resources
> - PDF: [[Author2024_FullTitle.pdf]]
> - MinerU Parse: [[Author2024_FullTitle]]
> - Zotero Notes: [[Author2024_FullTitle_zotero]]

## Central Thesis

{{centralThesis}}
*Extracted from MinerU Introduction/Abstract*
*Enhanced with 🔴 Red (Theory) annotations*

## Theoretical Framework

### Core Concepts
{{coreConcepts}}
*From MinerU main sections*
*Mapped to concept wikilinks: [[Concept1]], [[Concept2]]*

### Assumptions
{{assumptions}}
*Extracted from MinerU Theory section*

### Propositions
{{propositions}}
*From MinerU Theory/Framework section*

## Arguments

### Main Arguments
{{mainArguments}}
*Extracted from MinerU main body*
*Cross-referenced with 🟠 Orange (Analysis) annotations*

### Supporting Evidence
{{supportingEvidence}}
*From MinerU Evidence/Examples sections*
*Highlighted with 🟢 Green (Data) annotations*

### Counter-Arguments Addressed
{{counterArguments}}
*From MinerU Discussion section*

## Implications

### Theoretical Implications
{{theoreticalImplications}}
*Extracted from MinerU Discussion/Implications*
*Enhanced with 🔴 Red (Theory) annotations*

### Practical Implications
{{practicalImplications}}
*From MinerU Conclusion/Implications*
*Cross-referenced with 🩷 Magenta (Conclusion) annotations*

## Critique

{{critique}}
*User's critical analysis from annotations*

## Integration with Other Theories

{{theoreticalIntegration}}
*From MinerU Discussion/Related Work*
*Links to related papers: [[Paper1]], [[Paper2]]*
```

## Better Notes Compatible Template

This template works with the Better Notes plugin for Zotero and uses your custom color scheme:

**Color Mapping**:
- 🟡 **Yellow (#ffd400)**: 背景 (Background/Context)
- 🔴 **Red (#ff6666)**: 理论 (Theory)
- 🟢 **Green (#5fb236)**: 数据 (Data)
- 🔵 **Blue (#2ea8e5)**: 假设 (Hypothesis)
- 🟣 **Purple (#a28ae5)**: 实验 (Experiment)
- 🩷 **Magenta (#e56eee)**: 结论 (Conclusion)
- 🟠 **Orange (#ff9837)**: 分析 (Analysis)
- ⚪ **Gray (#aaaaaa)**: 重要 (Important)

```markdown
---
title: "{{title}}"
citekey: {{citekey}}
authors: [{{authors}}]
year: {{year}}
itemType: {{itemType}}
zotero: zotero://select/library/items/{{itemKey}}
mineru: "[[Author2024_FullTitle]]"
pdf: "Zotero Notes/Author2024_FullTitle.pdf"
zotero_notes: "[[Author2024_FullTitle_zotero]]"
betternotes: true
tags: [literature-note, {{autoTags}}]
---

# {{title}}

## 📄 元数据 (Metadata)

| 字段 | 内容 |
|------|------|
| 作者 | {{authors}} |
| 年份 | {{year}} |
| 期刊 | {{publicationTitle}} |
| DOI | [{{doi}}](https://doi.org/{{doi}}) |
| Zotero | [打开]({{zoteroLink}}) |
| PDF | [[Author2024_FullTitle.pdf]] |
| MinerU解析 | [[Author2024_FullTitle]] |
| Zotero笔记 | [[Author2024_FullTitle_zotero]] |

## 📝 摘要 (Abstract)

{{abstract}}
*从MinerU解析内容或Zotero元数据提取*

## 📊 论文内容 (Content from MinerU)

### 研究背景 (Background)
{{background}}
*从MinerU Introduction部分提取*

### 研究方法 (Methods)
{{methods}}
*从MinerU Methods部分提取*

### 主要结果 (Results)
{{results}}
*从MinerU Results部分提取*

### 关键图表 (Figures & Tables)
*从 `mineru-output/Author2024_FullTitle/` 文件夹嵌入*

- ![图1](../mineru-output/Author2024_FullTitle/figure_1.png)
- ![表1](../mineru-output/Author2024_FullTitle/table_1.png)

### 讨论与结论 (Discussion)
{{discussion}}
*从MinerU Discussion/Conclusion部分提取*

## 📌 标注与笔记 (Annotations)

### 🟡 背景 (Background/Context)
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

### ⚪ 重要 (Important)
{{grayAnnotations}}

## 💡 关键见解 (Key Insights)

{{insights}}
*综合MinerU内容和用户标注*

## 🔗 相关笔记 (Related Notes)

{{relatedNotes}}
*自动生成的概念链接: [[概念1]], [[概念2]]*

## ✍️ 我的笔记 (My Notes)

{{personalNotes}}

## ❓ 问题与思考 (Questions)

- 
- 

---
*创建时间: {{creationDate}}*
*最后修改: {{modificationDate}}*
```

## Canvas Template for Paper Collection

```json
{
  "nodes": [
    {
      "id": "{{generateId}}",
      "type": "text",
      "text": "# {{collectionName}}\n\n{{collectionDescription}}",
      "x": 0,
      "y": -400,
      "width": 600,
      "height": 200,
      "color": "5"
    },
    {
      "id": "{{paperNodeId}}",
      "type": "file",
      "file": "Literature Notes/{{paperFileName}}.md",
      "x": "{{xPosition}}",
      "y": "{{yPosition}}",
      "width": 400,
      "height": 300,
      "color": "{{yearColor}}"
    }
  ],
  "edges": [
    {
      "id": "{{edgeId}}",
      "fromNode": "{{sourceId}}",
      "toNode": "{{targetId}}",
      "label": "cites",
      "fromSide": "right",
      "toSide": "left"
    }
  ]
}
```

## Collection Index Template

```markdown
---
title: "{{collectionName}} - Index"
type: collection-index
date-created: {{date}}
tags: [collection, {{topic}}]
---

# {{collectionName}}

## Overview

{{collectionDescription}}

## Statistics

- **Total Papers**: {{paperCount}}
- **Date Range**: {{earliestYear}} - {{latestYear}}
- **Top Authors**: {{topAuthors}}
- **Key Topics**: {{keyTopics}}

## Papers by Year

### {{year}}
- [[Paper1]]
- [[Paper2]]

## Papers by Topic

### {{topic1}}
- [[PaperA]]
- [[PaperB]]

### {{topic2}}
- [[PaperC]]
- [[PaperD]]

## Key Concepts

- [[Concept1]] - appears in {{count}} papers
- [[Concept2]] - appears in {{count}} papers

## Knowledge Graph

![[{{collectionName}} Knowledge Graph.canvas]]

## Reading Progress

- [ ] [[Paper to read 1]]
- [x] [[Paper read 1]]
- [ ] [[Paper to read 2]]

## Notes

{{collectionNotes}}
```
