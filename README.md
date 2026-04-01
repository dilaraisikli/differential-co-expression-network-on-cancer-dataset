
# Differential Analyses of Gene Expression in Lung Adenocarcinoma

## Overview

This project analyzes gene expression differences between lung adenocarcinoma (LUAD) tissue and paired adjacent non-cancerous tissue samples using RNA-sequencing data. The analysis employs differential gene expression (DEG) analysis, gene co-expression networks, and differential co-expression networks to identify candidate biomarkers and therapeutic targets for LUAD.

## Background

Lung adenocarcinoma is the leading cause of cancer-related deaths globally, accounting for approximately 40% of all lung cancer cases. Despite current multimodal therapy approaches, LUAD patients show marginal improvements in survival time. Early diagnosis and identification of novel biomarkers are critical for improving patient outcomes.

## Dataset

- Source: The Cancer Genome Atlas (TCGA) project - LUAD dataset
- Data Portal: https://portal.gdc.cancer.gov/
- Sample Size: 57 patients with both cancer and normal tissue samples
- Total Genes: 17,224 genes
- Data Type: HTSeq-FPKM gene expression quantification

## Methods

### 1. Differentially Expressed Genes (DEG) Analysis

Identification of genes with significant expression differences between normal and cancer conditions using:

- Fold Change (FC) calculation: FC = log2(dataN) / log2(dataC)
- Student's t-test for p-value calculation
- FDR (False Discovery Rate) correction for multiple comparisons
- Threshold criteria: |fold change| > 2.5 and FDR ≤ 0.05

**Results:**
- Total identified genes: 494
- Upregulated genes: 237
- Downregulated genes: 257

### 2. Gene Co-expression Network Analysis

Construction of co-expression networks where:
- Each node represents a gene
- Edges connect genes with significant co-expression relationships
- Separate networks built for normal and cancer conditions

Network characteristics analyzed:
- Degree distribution
- Hub identification (top 5% nodes by degree)
- Centrality measures: degree, closeness, betweenness, eigenvector

**Cancer-specific hub genes (degree > 95%):**
BUB1B, KIF4A, DLGAP5, SKA3, EXO1, TPX2, HJURP, NCAPG, MELK, CKAP2L

**Normal-specific hub genes (degree > 95%):**
GTSE1, NDC80, CDC6, TOP2A, NUSAP1, CEP55, CDCA5, SKA1, TPX2, HJURP, NCAPG, MELK, CKAP2L

### 3. Differential Co-expression Network Analysis

Analysis of changes in co-expression relationships between conditions using:

- Fisher z-transformation for variance stabilization: z = 0.5 * log((1 + ρ)/(1 - ρ))
- Z-score computation to evaluate differential correlations
- Threshold: |Z| > 5

**Identified hub genes from differential co-expression network (degree > 95%):**
ZMYND10, NGEF, NEK2, CDHR3, PEBP4, PLPP2, SFTPC, SFTPB, BUB1, MAP7D2

## Key Findings

### Co-expression Network Findings

The co-expression network analysis identified distinct hub genes characterizing each condition. Five genes show high connectivity exclusively in cancer cells, while eight genes are hub genes only in normal cells. Several genes including TPX2, HJURP, NCAPG, MELK, and CKAP2L are hubs in both conditions but with different network contexts.

### Differential Co-expression Network Findings

The differential co-expression network identified 10 genes with significantly altered co-expression patterns between normal and cancer conditions. These genes are not present in the standard co-expression network hub sets, indicating they represent novel markers of disease-specific gene regulatory changes.

#### Notable Genes from Literature

- ZMYND10: Identified as a potential tumor suppressor gene frequently inactivated in lung cancer
- NEK2: One of the best proliferation markers in non-small cell lung cancer (NSCLC) prognosis; associated with poor outcomes and rapid relapse
- PEBP4: Promotes lung cancer cell proliferation and invasion via PI3K/Akt/mTOR signaling pathway; potential therapeutic target

## Key Distinction

The differential co-expression network identified genes with significant changes in co-expression patterns that are completely distinct from those identified through standard co-expression network analysis. This suggests that disease-specific biomarkers may be better identified through differential co-expression analysis rather than absolute network metrics.

## Project Structure

All code and key data files are available in the GitHub repository:
https://github.com/ceccaroni1884368/DE_TCGA-LUAD

## Authors

Dilara Isikli & Riccardo Ceccaroni

Group 08

## References

The analysis builds upon established bioinformatics methods for gene expression analysis and network-based approaches in cancer research. Key references include studies on LUAD biomarkers, gene co-expression networks, and differential expression analysis methodologies.

For detailed references, see the full research publication.

## Data Processing Pipeline

1. Download TCGA-LUAD data filtered by:
   - Transcriptome Profiling as data category
   - Gene Expression Quantification as data type
   - HTSeq-FPKM as workflow type
   - Samples with both cancer and normal tissue available

2. Differential Gene Expression Analysis
   - Calculate fold change and p-values
   - Apply FDR correction
   - Filter by thresholds

3. Co-expression Network Construction
   - Apply log2 transformation
   - Calculate gene-gene correlations
   - Build network with significance threshold
   - Analyze network topology and hubs

4. Differential Co-expression Analysis
   - Calculate correlation differences via Fisher z-transformation
   - Compute z-scores for statistical significance
   - Extract differential network and hub genes

5. Results Visualization
   - Network visualizations
   - Centrality measure comparisons
   - Subnetwork plots for top genes
   - Hub set comparisons

## Usage

Code implementation available in the GitHub repository. All analyses can be reproduced using the provided scripts and TCGA-LUAD dataset following the data filtering criteria specified above.

## License

Please refer to the GitHub repository for licensing information.
