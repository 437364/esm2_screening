# Protein Embedding-Based Detection of Sequence-Diverse Biosecurity Threats

A two-layer biosecurity screening pipeline that combines traditional sequence homology screening (SecureDNA) with protein embedding similarity analysis (ESM2) to detect functionally similar but sequence-diverse biosecurity threats.

## 🎯 Project Overview

Current DNA synthesis screening systems rely primarily on sequence homology to detect biosecurity threats, creating potential vulnerabilities to sophisticated evasion strategies. This project demonstrates that:

1. **ProteinMPNN-generated toxin variants** with 0-60% sequence identity to known toxins still cluster significantly closer to original toxin families than to neutral proteins in ESM2 embedding space
2. **Functional relationships are more conserved in embedding space than sequence space**
3. **Multi-modal screening approaches** could provide more robust biosecurity coverage against advanced evasion attempts

## 📁 Repository Structure

```
esm2_screening/
├── Biosecurity_Hackathon_Clean_Main_Pipeline.ipynb    # Main two-layer screening pipeline
├── ProteinMPNN.ipynb                                 # Toxin variant generation using ProteinMPNN
├── handle_fragments.ipynb                            # Multiple ORF detection and fragment analysis
├── check_embeddings_database.ipynb                   # Embedding space analysis and visualization
└── README.md                                         # This file
```

## 🔧 Key Components

### 1. Main Screening Pipeline (`Biosecurity_Hackathon_Clean_Main_Pipeline.ipynb`)

**Main Author:** [MAIN NOTEBOOK AUTHOR NAME - Primary contributor to the main screening pipeline]

A comprehensive biosecurity screening system with two complementary layers:

#### Layer 1: SecureDNA Homology Screening
- K-mer based sequence similarity detection
- Traditional approach for known threats and close variants
- Uses SecureDNA synthclient for regulatory screening

#### Layer 2: ESM2 Embedding Similarity
- Protein embedding-based threat detection
- Uses ESM2-650M model for functional relationship capture
- Cosine similarity scoring against toxin/neutral protein databases
- Can detect threats that evade sequence-based detection

**Key Features:**
- 6-frame DNA translation (forward and reverse complement)
- Configurable screening modes: `"full"`, `"securedna_only"`, `"embeddings_only"`
- Comprehensive result reporting with risk classification
- NIST dataset evaluation support

### 2. Variant Generation (`ProteinMPNN.ipynb`)

**Author:** [PROTEINMPNN NOTEBOOK AUTHOR - Primary contributor to protein variant generation]

Generates sequence-diverse toxin variants while preserving 3D structure:

- Uses ProteinMPNN v48_020 with temperature 0.25
- Creates 8 variants per target protein structure
- Filters based on sequence identity thresholds
- Demonstrates structure-function relationship preservation

### 3. Fragment Analysis (`handle_fragments.ipynb`)

**Author:** [FRAGMENT ANALYSIS AUTHOR - Primary contributor to multiple ORF detection and DNA fragment processing]

Handles complex DNA constructs with multiple coding regions:

- Multiple ORF detection across all 6 reading frames
- Handles untranslated regions and non-standard start positions
- Essential for real-world DNA synthesis scenarios
- Addresses reverse complement strand detection

### 4. Embedding Analysis (`check_embeddings_database.ipynb`)

**Author:** [EMBEDDINGS ANALYSIS AUTHOR - Primary contributor to database validation and embedding space visualization]

Visualizes and analyzes protein embedding space:

- PCA and UMAP visualization of embedding clusters
- Demonstrates toxin variant clustering behavior
- Validates embedding-based classification approach
- Statistical analysis of similarity distributions

## 🗄️ Databases

The project uses pre-computed ESM2 embeddings:

- **Toxin Database**: 7,000+ reviewed UniProt proteins (KW-0800)
- **Neutral Database**: 25,000+ reviewed proteins (excluding toxins/virulence factors)
- **Critical Proteins**: Manually curated high-risk proteins
- **Generated Variants**: 2,440 ProteinMPNN-generated sequence-diverse variants

## 📊 Key Results

### Embedding Space Analysis
- **96.8%** of sequence-diverse variants (2,361/2,440) have top similarity matches in toxin database
- Variants with **>30% sequence identity** to originals show strongest clustering
- Clear separation between toxin variants and neutral proteins in PCA space

### Pipeline Performance
- Successfully processes DNA sequences through both screening layers
- Demonstrates potential to catch threats missed by homology-based screening
- Preliminary NIST dataset evaluation conducted (with noted ground truth alignment challenges)

## 🚀 Quick Start

### Prerequisites
```bash
pip install transformers torch biopython requests numpy scipy scikit-learn joblib matplotlib umap-learn
```

### SecureDNA Setup (Optional but Recommended)
```bash
# Install SecureDNA synthclient
curl -sSL https://securedna.github.io/ppa/deb/securedna-keyring.gpg | sudo tee /usr/share/keyrings/securedna-keyring.gpg > /dev/null
echo "deb [signed-by=/usr/share/keyrings/securedna-keyring.gpg] https://securedna.github.io/ppa/deb ./" | sudo tee /etc/apt/sources.list.d/securedna.list > /dev/null
sudo apt update && sudo apt install -y synthclient
```

### Basic Usage
```python
# Load the main pipeline
from main_pipeline import screen_sequence

# Screen a DNA sequence
dna_sequence = "ATGGCCATATTAAACTGATGAACCCGCAGCGC..."
result = screen_sequence(dna_sequence, mode="full")

print(f"Risk Assessment: {result.combined_risk}")
print(f"ESM2 Score: {result.functional_score}")
print(f"SecureDNA Flagged: {result.securedna_flagged}")
```

## 🔬 Methodology

### 1. Variant Generation Process
1. Select toxin structures from PDB
2. Generate sequence variants using ProteinMPNN
3. Filter variants by sequence identity thresholds
4. Exclude high internal similarity sequences

### 2. Embedding Analysis
1. Compute ESM2 embeddings for all proteins
2. Apply reference mean subtraction and L2 normalization
3. Calculate cosine similarities to toxin/neutral databases
4. Generate differential scores (S_toxin - S_neutral)

### 3. Multi-Layer Screening
1. **DNA Translation**: 6-frame translation to find longest ORF
2. **Layer 1**: SecureDNA k-mer homology screening
3. **Layer 2**: ESM2 embedding similarity analysis
4. **Risk Assessment**: Combined verdict from both layers

## ⚠️ Limitations & Future Work

### Current Limitations
- **Incomplete Integration**: Multiple ORF handling not fully integrated into main pipeline
- **Simple Classification**: Cosine similarity-based rather than trained ML classifier
- **Limited Validation**: Focused on well-characterized toxin families
- **Computational Cost**: ESM2 embedding computation is resource-intensive
- **SecureDNA Access**: API access challenges during development

### Prioritized Future Work
1. **Complete ML Classifier Training** with attention pooling mechanisms
2. **Full Multi-ORF Integration** for realistic DNA synthesis scenarios  
3. **Systematic Validation** across broader threat categories
4. **Performance Optimization** for real-time screening applications
5. **Codon Optimization** for organism-specific synthesis contexts

## 🔒 Security & Dual-Use Considerations

This work has a primarily **defensive focus** aimed at improving biosecurity screening capabilities. Key considerations:

- **No Functional Validation**: Generated sequences not tested for biological activity
- **Computational Focus**: Structural preservation ≠ functional preservation
- **Responsible Disclosure**: Findings shared with biosecurity research community
- **Community Benefit**: Enhances DNA synthesis ecosystem security

## 🏆 Hackathon Context

**Event**: Apart Research AI×Bio Biosecurity Hackathon  
**Duration**: April 24-26, 2026  
**Team**: Polina Shevyakova¹, Henry Ward, Elina Shaniiazova², Marie Krátká³  

**Affiliations**:
- ¹ Higher School of Economics, Faculty of Biology
- ² Constructor University Bremen  
- ³ Masaryk University

## 📖 References

- Dauparas, J., et al. (2022). Robust deep learning–based protein sequence design using ProteinMPNN. *Science*, 378(6615), 49-56.
- Lin, Z., et al. (2023). Evolutionary-scale prediction of atomic-level protein structure with a language model. *Science*, 379(6637), 1123-1130.
- SecureDNA. (2024). Safeguarding DNA synthesis with digital signatures and similarity detection.

## 📧 Contact

For questions about this research, please refer to the full submission document or contact the team through the hackathon organizers.

---

**Note**: This project was developed during a 3-day hackathon. While the core findings are promising, further validation and development are needed for production deployment.
