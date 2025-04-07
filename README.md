# DeNSAS: De Novo Sequence Annotation System

## Overview

DeNSAS (De Novo Sequence Annotation System) is a comprehensive, reference-free pipeline designed for functional annotation of transcripts, proteins, and genes in genome assemblies that lack reference annotation. Developed in-house, this automated system integrates multiple public databases and computational tools to provide accurate functional characterization of sequences without requiring a reference genome.

## Core Functionality

DeNSAS employs a 6-step process using custom Perl scripts and locally built databases to provide:

1. **Sequence Description Assignment**: Integrating results from multiple database searches to assign comprehensive functional descriptions to sequences
2. **Gene Ontology (GO) Annotation**: Assignment of GO terms for biological process, molecular function, and cellular component
3. **Protein Domain Identification**: Recognition of conserved protein domains using PFAM
4. **RNA Family Classification**: Identification of RNA families using RFAM
5. **Protease Classification**: Specialized annotation of peptidases using MEROPS
6. **Gene Family Assignment**: Characterization of gene families based on sequence similarity

## Key Features

- **Reference-Free Annotation**: Functions independently without requiring a reference genome or annotation
- **Integrative Approach**: Combines data from multiple databases including PFAM, RFAM, UniProt, InterPro, MEROPS, and RefSeq
- **Novel Gene Identification**: Capable of characterizing potentially novel genes and duplication events
- **Comprehensive Output**: Provides detailed annotation including:
  - Full gene names and unique IDs (when close matches exist)
  - Protein domains and motifs
  - Gene family assignments
  - GO term classifications
  - RNA family patterns

## Advantages Over Existing Tools

- Unlike reference-based tools (e.g., OrthoFinder, CRB-Blast), DeNSAS does not require an existing reference strain to guide annotation
- Compared to other reference-free annotation pipelines (e.g., PANNZER2), DeNSAS offers improved accuracy through its integrative nature and multi-database approach
- Custom filtering thresholds ensure high-quality annotations with minimal false positives

## Technical Implementation

DeNSAS employs stringent similarity thresholds:
- BLAST searches use an e-value cut-off of 10e⁻⁵ and HSP similarity threshold of 80%
- Sequence descriptions employ more restrictive thresholds (e-value 1e-10 and 90% similarity)
- RNA and protein family identification filtered by Expectation Value (1e-10)
- Transparent labeling of sequences with insufficient database matches as "UNKNOWN DESCRIPTION"

## Applications

- Annotation of non-model organisms
- Characterization of newly sequenced genomes
- Identification of novel genes and gene families
- Comparative genomic analyses
- Functional studies of transcriptomes
