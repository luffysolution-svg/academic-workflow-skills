# Example Workflows

## Example 1: Quick Paper Import from DOI

**User**: "Import the paper with DOI 10.1038/s41586-024-07487-w"

**Workflow**:
```
1. Download PDF: mcp__ai4scholar__download_pdf_by_doi
   - Save to: {vault}/Zotero Notes/Author2024_FullTitle.pdf
2. Parse PDF: Use MinerU CLI with API token
   - Output: {vault}/mineru-output/Author2024_FullTitle.md
   - Rename from original filename to full title format
3. Read MinerU output: Extract sections (Abstract, Intro, Methods, Results, Discussion)
4. List figures/tables: From mineru-output/Author2024_FullTitle/ folder
5. Search Zotero: search_library (check if exists)
6. Get metadata from Semantic Scholar: search_semantic
7. Generate comprehensive note combining:
   - MinerU parsed content
   - Embedded figures and tables
   - Metadata from Semantic Scholar
8. Save to vault: Literature/Papers/Author2024_FullTitle.md
```

**Generated Note Preview**:
```markdown
---
title: "Scaling Laws for Neural Language Models"
authors: [Kaplan, J., McCandlish, S., et al.]
year: 2024
doi: 10.1038/s41586-024-07487-w
zotero: zotero://select/library/items/ABC123
mineru: "[[Kaplan2024_Scaling_Laws_for_Neural_Language_Models]]"
pdf: "Zotero Notes/Kaplan2024_Scaling_Laws_for_Neural_Language_Models.pdf"
zotero_notes: "[[Kaplan2024_Scaling_Laws_for_Neural_Language_Models_zotero]]"
tags: [literature-note, machine-learning, scaling-laws]
---

# Scaling Laws for Neural Language Models

> [!info] Metadata
> - **Authors**: Jared Kaplan, Sam McCandlish, et al.
> - **Year**: 2024
> - **Publication**: Nature
> - **DOI**: [10.1038/s41586-024-07487-w](https://doi.org/10.1038/s41586-024-07487-w)
> - **PDF**: [[Kaplan2024_Scaling_Laws_for_Neural_Language_Models.pdf]]
> - **MinerU Parse**: [[Kaplan2024_Scaling_Laws_for_Neural_Language_Models]]
> - **Zotero Notes**: [[Kaplan2024_Scaling_Laws_for_Neural_Language_Models_zotero]]

## Abstract
*Extracted from MinerU parsed content:*

We study empirical scaling laws for language model performance on the cross-entropy loss. The loss scales as a power-law with model size, dataset size, and the amount of compute used for training...

## 📊 Content Analysis (from MinerU)

### Research Background
*From MinerU Introduction section:*

Recent advances in neural language models have shown remarkable improvements in performance. However, the relationship between model scale and performance remains poorly understood...

### Methodology
*From MinerU Methods section:*

We trained over 100 language models ranging from 768 parameters to 1.5 billion parameters on datasets from 22 million to 23 billion tokens...

### Main Results
*From MinerU Results section:*

Model performance scales predictably with compute, dataset size, and parameters. The optimal allocation of compute budget follows power laws...

### Key Figures
- ![Figure 1: Scaling curves](../mineru-output/Kaplan2024_Scaling_Laws_for_Neural_Language_Models/figure_1.png)
  *Loss vs compute for different model sizes*
- ![Figure 2: Optimal allocation](../mineru-output/Kaplan2024_Scaling_Laws_for_Neural_Language_Models/figure_2.png)
  *Optimal model size and dataset size given compute budget*

## Key Takeaways
- Model performance scales predictably with compute, dataset size, and parameters
- Optimal allocation of compute budget follows power laws
- Larger models are more sample-efficient
```

---

## Example 2: Extract Annotations from Zotero

**User**: "Extract my annotations from the CRISPR paper in Zotero"

**Workflow**:
```
1. Search Zotero: search_library(query="CRISPR")
2. Present matches, user selects item
3. Get details: get_item_details(itemKey)
4. Get annotations: get_annotations(itemKey)
5. Parse PDF with MinerU if needed, rename to Author2024_FullTitle.md
6. Read MinerU output: Extract sections and figures
7. Organize annotations by Better Notes color scheme
8. Generate comprehensive literature note combining:
   - MinerU parsed content (Background, Methods, Results, Discussion)
   - Embedded figures and tables
   - User's color-coded annotations mapped to sections
9. Save to: Literature/Papers/Author2024_FullTitle.md
10. Save Zotero data: Zotero Notes/Author2024_FullTitle_zotero.md
```

**Generated Note with Annotations**:
```markdown
---
title: "CRISPR-Cas9 Gene Editing"
authors: [Doudna, J., Charpentier, E.]
year: 2014
zotero: zotero://select/library/items/XYZ789
mineru: "[[Doudna2014_CRISPR_Cas9_Gene_Editing]]"
pdf: "Zotero Notes/Doudna2014_CRISPR_Cas9_Gene_Editing.pdf"
zotero_notes: "[[Doudna2014_CRISPR_Cas9_Gene_Editing_zotero]]"
tags: [literature-note, crispr, gene-editing]
---

# CRISPR-Cas9 Gene Editing

> [!info] Metadata
> - **PDF**: [[Doudna2014_CRISPR_Cas9_Gene_Editing.pdf]]
> - **MinerU Parse**: [[Doudna2014_CRISPR_Cas9_Gene_Editing]]
> - **Zotero Notes**: [[Doudna2014_CRISPR_Cas9_Gene_Editing_zotero]]

## 📌 我的标注 (Annotations)

### 🔴 理论 (Theory)

> "The CRISPR-Cas9 system provides unprecedented precision in genome editing"
> — Page 3, Highlighted on 2024-03-15

**My note**: This is the core innovation - precision is key advantage over previous methods

> "Off-target effects remain a significant concern"
> — Page 12, Highlighted on 2024-03-15

**My note**: Need to investigate mitigation strategies

### 🟡 背景 (Background)

> "Guide RNA design is crucial for specificity"
> — Page 5

> "Delivery mechanisms vary by cell type"
> — Page 8

### 🟣 问题 (Question)

- How does this compare to base editing?
- Could this be applied to [[Mitochondrial DNA Editing]]?
- Related to [[Doudna 2020 - CRISPR Applications]]

## 📊 Content Analysis (from MinerU)

### Research Background
*From MinerU Introduction:*

The CRISPR-Cas9 system is an adaptive immune system in bacteria that has been repurposed for genome editing. Previous methods like ZFNs and TALENs were limited by...

### Methodology
*From MinerU Methods:*

We designed guide RNAs targeting specific genomic loci. The Cas9 protein was expressed in mammalian cells and complexed with guide RNAs...

### Main Results
*From MinerU Results:*

CRISPR-Cas9 achieved 80-90% editing efficiency in target cells. Off-target effects were observed at a rate of 0.1-1% depending on guide RNA design...

### Key Figures
- ![Figure 1: CRISPR mechanism](../mineru-output/Doudna2014_CRISPR_Cas9_Gene_Editing/figure_1.png)
- ![Figure 2: Editing efficiency](../mineru-output/Doudna2014_CRISPR_Cas9_Gene_Editing/figure_2.png)
```

---

## Example 3: Batch Process Zotero Collection

**User**: "Process all papers in my 'Deep Learning' collection"

**Workflow**:
```
1. Get collections: get_collections()
2. Find "Deep Learning" collection
3. Get all items: search_library(collection="Deep Learning")
4. For each of 15 papers:
   a. Get details and annotations
   b. Parse PDF with MinerU, rename to Author2024_FullTitle.md
   c. Read MinerU output and extract sections
   d. Extract key concepts from content
   e. Generate comprehensive literature note combining:
      - MinerU parsed content
      - Embedded figures and tables
      - User's Zotero annotations
   f. Save to: Literature/Papers/Author2024_FullTitle.md
   g. Save Zotero data: Zotero Notes/Author2024_FullTitle_zotero.md
   h. Track concepts across papers
5. Identify common concepts: ["Transformer", "Attention", "Backpropagation"]
6. Create concept notes
7. Add wikilinks between related papers
8. Generate collection canvas
9. Create index note
```

**Generated Collection Index**:
```markdown
---
title: Deep Learning Collection
tags: [collection, deep-learning]
papers: 15
date-created: 2024-04-18
---

# Deep Learning Collection

## Overview
Collection of 15 papers on deep learning fundamentals and applications.

## Key Concepts
- [[Transformer Architecture]] (8 papers)
- [[Attention Mechanism]] (10 papers)
- [[Backpropagation]] (5 papers)
- [[Gradient Descent]] (7 papers)

## Papers by Topic

### Foundational Papers
- [[Vaswani2017_AttentionIsAllYouNeed]]
- [[Hinton2006_DeepLearning]]
- [[LeCun1998_GradientBasedLearning]]

### Recent Advances
- [[Brown2020_LanguageModelsAreFewShot]]
- [[Dosovitskiy2020_ImageWorth16x16Words]]

### Applications
- [[Jumper2021_HighlyAccurateProtein]]
- [[Silver2016_MasteringGameGo]]

## Citation Network
![[Deep Learning Knowledge Graph.canvas]]

## Reading Progress
- ✅ Read: 8 papers
- 📖 Reading: 3 papers
- 📋 To Read: 4 papers
```

**Generated Canvas** (Deep Learning Knowledge Graph.canvas):
```json
{
  "nodes": [
    {
      "id": "header",
      "type": "text",
      "text": "# Deep Learning Knowledge Graph\n\n15 papers | 3 core concepts",
      "x": 0,
      "y": -500,
      "width": 800,
      "height": 150,
      "color": "5"
    },
    {
      "id": "paper-vaswani2017",
      "type": "file",
      "file": "Literature/Papers/Vaswani2017_AttentionIsAllYouNeed.md",
      "x": -400,
      "y": 0,
      "width": 350,
      "height": 250,
      "color": "1"
    },
    {
      "id": "concept-attention",
      "type": "text",
      "text": "## Attention Mechanism\n\nCore concept in modern deep learning\n\n**Used in**: 10 papers\n**Key innovation**: Self-attention",
      "x": 100,
      "y": 0,
      "width": 300,
      "height": 200,
      "color": "3"
    },
    {
      "id": "paper-brown2020",
      "type": "file",
      "file": "Literature/Papers/Brown2020_LanguageModelsAreFewShot.md",
      "x": -400,
      "y": 350,
      "width": 350,
      "height": 250,
      "color": "2"
    }
  ],
  "edges": [
    {
      "id": "edge-1",
      "fromNode": "paper-vaswani2017",
      "toNode": "concept-attention",
      "label": "introduces",
      "fromSide": "right",
      "toSide": "left"
    },
    {
      "id": "edge-2",
      "fromNode": "paper-brown2020",
      "toNode": "paper-vaswani2017",
      "label": "cites",
      "fromSide": "top",
      "toSide": "bottom",
      "toEnd": "arrow"
    },
    {
      "id": "edge-3",
      "fromNode": "paper-brown2020",
      "toNode": "concept-attention",
      "label": "uses",
      "fromSide": "right",
      "toSide": "left"
    }
  ]
}
```

---

## Example 4: Build Knowledge Graph from Search

**User**: "Create a knowledge graph for recent papers on protein folding"

**Workflow**:
```
1. Search multiple sources:
   - search_semantic(query="protein folding", year="2020-", max_results=20)
   - search_pubmed(query="protein folding prediction", sort="date", max_results=20)
2. Rank by citations and relevance
3. Select top 10 papers
4. For each paper:
   a. Download PDF: download_pdf_by_doi or read_semantic_paper
   b. Parse: mcp__mineru__parse_documents
   c. Check Zotero: search_library
   d. Generate literature note
   e. Extract concepts: ["AlphaFold", "Deep Learning", "Structure Prediction"]
5. Get citation relationships:
   - get_semantic_citations for each paper
   - get_semantic_references for each paper
6. Build citation network
7. Create concept notes with definitions
8. Generate canvas with:
   - Paper nodes (colored by year)
   - Concept nodes
   - Citation edges
   - Thematic groups
9. Create index note
```

**Generated Knowledge Graph**:
- 10 paper notes with full annotations
- 5 concept notes (AlphaFold, Deep Learning, MSA, Structure Prediction, Protein Dynamics)
- 1 canvas showing citation network
- 1 index note linking everything

**Concept Note Example** (AlphaFold.md):
```markdown
---
title: AlphaFold
type: concept
field: computational-biology
tags: [concept, protein-folding, deep-learning]
---

# AlphaFold

## Definition
Deep learning system for predicting 3D protein structures from amino acid sequences with unprecedented accuracy.

## Key Papers
- [[Jumper2021_HighlyAccurateProtein]] - AlphaFold 2 (seminal paper)
- [[Evans2022_ProteinComplexPrediction]] - AlphaFold-Multimer
- [[Varadi2022_AlphaFoldProteinStructure]] - AlphaFold Database

## Core Innovation
- Uses attention mechanisms to process multiple sequence alignments (MSA)
- Predicts inter-residue distances and angles
- Iterative refinement of structure

## Impact
- Solved 50-year protein folding problem
- Enabled structure prediction for entire proteomes
- Accelerated drug discovery and protein engineering

## Related Concepts
- [[Multiple Sequence Alignment]]
- [[Transformer Architecture]]
- [[Structure Prediction]]
- [[Deep Learning in Biology]]

## Applications
- Drug target identification
- Protein engineering
- Understanding disease mechanisms
```

---

## Example 5: Update Existing Notes with New Annotations

**User**: "Update my literature notes with new Zotero annotations"

**Workflow**:
```
1. Get all literature notes from vault
2. Extract Zotero item keys from frontmatter
3. For each note:
   a. Get latest annotations: search_annotations(itemKey)
   b. Compare with existing annotations in note
   c. If new annotations found:
      - Add to appropriate section (by color)
      - Update modification date
      - Preserve existing personal notes
4. Report: "Updated 5 notes with 12 new annotations"
```

---

## Example 6: Search and Compare Papers

**User**: "Find papers comparing CRISPR and base editing, create comparison note"

**Workflow**:
```
1. Search: search_semantic(query="CRISPR vs base editing comparison")
2. Search: search_pubmed(query="base editing CRISPR comparison")
3. Present top 5 papers
4. User selects 3 papers
5. Import all 3 papers
6. Generate individual literature notes
7. Create comparison note:
   - Extract methodology from each
   - Compare results
   - Synthesize findings
   - Create comparison table
8. Link all papers in comparison note
```

**Generated Comparison Note**:
```markdown
---
title: CRISPR vs Base Editing Comparison
type: synthesis-note
papers: 3
tags: [comparison, crispr, base-editing]
---

# CRISPR vs Base Editing: Comparative Analysis

## Papers Analyzed
- [[Komor2016_ProgrammableEditingSingle]]
- [[Gaudelli2017_ProgrammableCGBase]]
- [[Anzalone2019_SearchAndReplaceGenome]]

## Comparison Table

| Aspect | CRISPR-Cas9 | Base Editing | Prime Editing |
|--------|-------------|--------------|---------------|
| **Mechanism** | DSB + HDR | Direct base conversion | Reverse transcriptase |
| **Precision** | Moderate | High | Very High |
| **Off-targets** | Higher | Lower | Lowest |
| **Editable changes** | Insertions, deletions | Single base | All types |
| **Efficiency** | Variable | High | Moderate |

## Key Findings

### Advantages of Base Editing
- No double-strand breaks (safer)
- Higher precision for point mutations
- Lower off-target effects

### Advantages of CRISPR-Cas9
- More versatile (any edit type)
- Established protocols
- Wider range of applications

### Prime Editing Innovation
- Combines benefits of both
- "Search and replace" capability
- Still developing

## Synthesis
[Your analysis combining insights from all three papers...]

## Related Notes
- [[Gene Editing Technologies]]
- [[Therapeutic Applications]]
```

---

## Example 7: Create Reading List from Collection

**User**: "Create a prioritized reading list from my 'To Read' collection"

**Workflow**:
```
1. Get "To Read" collection: get_collections()
2. Get all items: search_library(collection="To Read")
3. For each paper:
   - Get citation count (from Semantic Scholar)
   - Get publication year
   - Check if cited by papers I've already read
4. Rank by:
   - Citation count (weight: 0.4)
   - Recency (weight: 0.3)
   - Relevance to read papers (weight: 0.3)
5. Generate reading list note with priorities
```

**Generated Reading List**:
```markdown
---
title: Prioritized Reading List
collection: To Read
papers: 25
generated: 2024-04-18
---

# Prioritized Reading List

## High Priority (Read First)

### 1. [[Vaswani2017_AttentionIsAllYouNeed]] ⭐⭐⭐
- **Citations**: 50,000+
- **Year**: 2017
- **Why**: Foundational paper, cited by 5 papers you've read
- **Estimated time**: 2 hours

### 2. [[Brown2020_LanguageModelsAreFewShot]] ⭐⭐⭐
- **Citations**: 10,000+
- **Year**: 2020
- **Why**: Recent breakthrough, highly relevant to your research
- **Estimated time**: 3 hours

## Medium Priority

### 3. [[Dosovitskiy2020_ImageWorth16x16Words]] ⭐⭐
- **Citations**: 8,000+
- **Year**: 2020
- **Why**: Extends transformers to vision

[... continues ...]

## Reading Schedule

- **Week 1**: Papers 1-3 (High priority)
- **Week 2**: Papers 4-7 (Medium priority)
- **Week 3**: Papers 8-12 (Lower priority)

## Progress Tracking

- [ ] Paper 1
- [ ] Paper 2
- [ ] Paper 3
```

These examples demonstrate the full range of capabilities from simple imports to complex knowledge graph generation and synthesis.
