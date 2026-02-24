# StructuralFusion-IE: A Structure-Aware Neural Framework for Web Field Extraction
*Version: 1.0*

This artifact package contains all reproducible components associated with the StructuralFusion-IE prototype, as documented in the accompanying thesis:

Structure-Aware Neural Information Extraction from Web Pages: A Text–DOM Fusion Prototype

Aref Alshanty — aref_268862

Syrian Virtual University , Web scinece master degree, 2026

## StructuralFusion-IE integrates:
 - Transformer-based textual embeddings
 - DOM graph structural encoding
 - Structural attention mechanisms
 - Text–Structure fusion layers
 - Cross-site evaluation protocol
 - Node-level and Page-level performance analysis

The objective is to evaluate whether incorporating DOM structural signals improves robustness and accuracy in web field extraction tasks.

## 1. System Requirements

**Python:** 3.10+
**OS:** Windows 10 / Windows 11
**Hardware:**
 - GPU Optional (CUDA-compatible, 6GB+ VRAM)
 - CPU-only mode supported (slower training)
 - RAM: ≥ 8 GB recommended

**Dependencies**
Main dependencies include:
```
torch >= 2.2
torch-geometric >= 2.5
numpy
scikit-learn
networkx
beautifulsoup4
lxml
matplotlib
seaborn
tqdm
```
Install using:
``` bash
pip install -r requirements.txt
```
**Virtual Environment (Recommended)**

For full reproducibility and to avoid dependency conflicts, create an isolated virtual environment:
```
python -m venv SFv1
source SFv1/Scripts/activate    # Windows
pip install -r requirements.txt
```
All experiments in this thesis were executed within a dedicated virtual environment to ensure controlled dependency management.

## 2. Dataset Requirements

The dataset used in this thesis is publicly available via Academic Torrents:

Dataset Download Link:
https://academictorrents.com/download/411576c7e80787e4b40452360f5f24acba9b5159.torrent

Download the torrent file and extract the dataset into:

SWDE_Dataset/

The dataset must contain:
 - Raw HTML pages
 - Corresponding node-level labels
 - Site separation (for cross-site evaluation)

# 3. Preprocessing Pipeline

The preprocessing pipeline includes:
 - HTML parsing using BeautifulSoup
 - DOM tree construction
 - Node extraction
 - Text cleaning
 - Graph edge construction (Parent–Child–Sibling)
 - Node feature generation

# 4. Model Architectures

The artifact includes three models:

 1. Text-only Baseline
    - Transformer-based node text encoding without structural signals.
 2. Structure-only Baseline
    - Graph Neural Network over DOM structure without textual embeddings.
 3. StructuralFusion Model (Proposed)
    - Text embedding (768-dim)
    - Structural embedding (256-dim)
    - 2 Graph layers
    - 4 attention heads
    - Fusion projection (1024 → 512)
    - Node-level classification head
    
All models share identical training hyperparameters for fair comparison.


# 5. Reproducing the Pipeline

Run:
```
main.ipynb
```
Produces: everything on this prototype as a saved files on local storage

Note: That processing large number of HTML pages might use more disk space

# 6. Limitations
 - Evaluation performed primarily under cross-site setup
 - No large-scale pretraining beyond baseline embeddings
 - Performance sensitive to HTML noise quality
 - Deeply nested DOM structures may reduce stability

# 7. Contact

For questions, checkpoints, or additional materials:
 - **Aref Alshanty**
 - ***Email:*** aref_268862@svuonline.org
 - ***Institution:*** Syrian Virtual University
 - ***Year:*** 2026
