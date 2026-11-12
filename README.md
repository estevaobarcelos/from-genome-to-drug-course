# From Genome to Drug — Bioinformatics & Omics Sciences

A Master's-level course in Pharmaceutical Biotechnology tracing the full journey from genome to drug, using ipilimumab and CTLA-4 as a clinical thread across all six lessons.

---

## Course Overview

This six-lesson course walks Master's students in Pharmaceutical Biotechnology from raw genomic data through to a clinically approved drug. Every lesson uses a single unifying case study — ipilimumab (Yervoy), the first-in-class CTLA-4 checkpoint inhibitor — so each computational method is immediately grounded in a real therapeutic question.

---

## Lessons at a Glance

| Lesson | Title | Key Topics | Exercises / Tools |
| --- | --- | --- | --- |
| I | Introduction to Bioinformatics & R | R data structures, ggplot2 visualisation, the central dogma, omics layers | `Exercise_01`, `Exercise_02` |
| II | Sequence Analysis | BLAST (BLASTn / BLASTp), pairwise and multiple sequence alignment (ClustalOmega, EMBOSS Needle), mutation detection, NCBI queries via rentrez | `Exercise_03`, `Exercise_04`; Lesson 2 scripts |
| III | Transcriptomics — RNA-seq Pipeline | RNA-seq workflow (FastQC → STAR → featureCounts), GEO data retrieval (GSE114716), count-matrix construction; ipilimumab CD4⁺ T-cell dataset | `Lesson_3` R script |
| IV | Transcriptomics — Functional Enrichment | p-value, log2FC, adjusted p-value; DESeq2 (normalisation → dispersion → Wald test → BH correction); volcano plots; Gene Ontology (ORA); Gene Set Enrichment Analysis (GSEA desktop + Hallmark gene sets) | `Lesson_4` R script; GSEA desktop app |
| V | Proteomics — Protein Visualisation | Translation, protein homology, UniProt / PDB databases, X-ray crystallography, antibody structure (CDRs, Kabat numbering), ipilimumab–CTLA-4 complex (5TRU); ChimeraX visualisation | `Exercise_05`, `Exercise_06`; ChimeraX |
| VI | Structural Modelling & Nanobodies | PD-1 nanobody sequences; AlphaFold structure prediction; visualisation of nanobody–PD-1 interaction models (C11, C12) | `Lesson_6` FASTA + CIF files; ChimeraX |

---

## Tools and Packages

**R packages**

| Package | Purpose |
| --- | --- |
| `ggplot2` | Data visualisation |
| `rentrez` | NCBI database queries |
| `Biostrings` | Biological sequence handling |
| `msa` | Multiple sequence alignment (ClustalOmega via R) |
| `ape` | Phylogenetic trees (Neighbor-Joining) |
| `pheatmap` | Heatmaps (pairwise identity matrices) |
| `bio3d` | PDB structure download, CDR extraction |
| `seqinr` | Sequence manipulation |
| `DESeq2` | Differential expression (Negative Binomial GLM, BH correction) |
| `clusterProfiler` | Gene Ontology over-representation analysis |
| `survival` | Kaplan–Meier and Cox survival analysis |

**External tools**

| Tool | Use in course |
| --- | --- |
| BLAST (NCBI) | Nucleotide and protein sequence identification |
| ClustalOmega | Multiple sequence alignment |
| EMBOSS Needle | Pairwise global alignment |
| GSEA desktop app (v4.3+) | Gene Set Enrichment Analysis with MSigDB Hallmark sets |
| UCSF ChimeraX | 3-D protein structure visualisation and CDR highlighting |
| AlphaFold / ColabFold | Protein structure prediction (Lesson VI) |

**Databases**

| Database | URL |
| --- | --- |
| NCBI (GenBank, PubMed) | https://www.ncbi.nlm.nih.gov |
| UniProtKB / Swiss-Prot | https://www.uniprot.org |
| RCSB Protein Data Bank | https://www.rcsb.org |
| GEO (Gene Expression Omnibus) | https://www.ncbi.nlm.nih.gov/geo |
| MSigDB | https://www.gsea-msigdb.org |
| TCGA (via UCSC Xena) | https://xenabrowser.net |

---

## Data

| Dataset | Lessons | Description | Source |
| --- | --- | --- | --- |
| GSE114716 | III, IV | RNA-seq of CD4⁺ T cells from metastatic melanoma patients at baseline (T0) and after 3 doses of ipilimumab (T1); Illumina HiSeq 2500; platform GPL16791 | [Goswami et al. 2018, JCI](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE114716) |
| TCGA LAML | — | Acute myeloid leukaemia cohort: expression matrix, somatic mutations, clinical annotations, and survival data; used for TP53 mutation survival analysis | [UCSC Xena / GDC](https://xenabrowser.net/datapages/?cohort=TCGA%20Acute%20Myeloid%20Leukemia%20(LAML)) |
| GSE238230 | — | Adipogenesis RNA-seq with TP53 perturbation; supplementary analysis | [GEO GSE238230](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE238230) |
| PDB 5TRU | V | Crystal structure of ipilimumab Fab bound to human CTLA-4; X-ray diffraction, 3.00 Å resolution | [RCSB PDB 5TRU](https://www.rcsb.org/structure/5TRU) |
| UniProtKB P16410 / P09793 / P42072 / Q9MYX7 | V | CTLA-4 protein sequences for Human, Mouse, Rabbit, Pig | [UniProt](https://www.uniprot.org) |

---

## Getting Started

1. **Clone the repository**

```bash
git clone https://github.com/estevaobarcelos/from-genome-to-drug-course.git
cd from-genome-to-drug-course
```

2. **Install R dependencies** — open RStudio and run the install block at the top of whichever exercise script you are working on. The packages most commonly required are:

```r
install.packages(c("ggplot2", "rentrez", "ape", "pheatmap", "seqinr"))

if (!requireNamespace("BiocManager", quietly = TRUE)) install.packages("BiocManager")
BiocManager::install(c("Biostrings", "msa", "bio3d", "DESeq2", "clusterProfiler"))
```

3. **Follow lessons in order** — each lesson's PDF (`Genome_to_Drug_I.pdf` … `Genome_to_Drug_VI.pdf`) explains the theory; the matching exercise script provides hands-on practice.

4. **External tools to install separately**
   - [UCSF ChimeraX](https://www.cgl.ucsf.edu/chimerax/download.html) — free for academic use
   - [GSEA desktop app](https://www.gsea-msigdb.org) — free registration required

