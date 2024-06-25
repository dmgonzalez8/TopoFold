## Generative Models for Protein Sequences
![./images/alphafold.png]
#### [Eren Bardak](https://github.com/eren-bardak) and Daniel Gonzalez
#### University of San Francisco

### Overview
In this project, we explore two cutting-edge methods for generating novel protein sequences. We extend and refine the Struct2Seq model, which incorporates Transformers and a Message Passing Neural Network (MPNN) for predicting novel Multiple Sequence Alignments (MSA) from given protein sequences. Additionally, we improve upon ProtGPT2, aimed at generating entirely novel protein sequences.

### Installation
Before starting, ensure all required packages are installed:
```bash
pip install biopython
pip install nglview
conda install -c conda-forge nglview
```

### Dataset
We utilize the ProteinNet CASP12 dataset, which provides protein sequences along with Position Specific Scoring Matrix (PSSM) and structural data. Detailed documentation is available through the [ProteinNet resource](https://github.com/aqlaboratory/proteinnet).

### Usage
After processing the data, the following scripts are used for training and prediction:
- **Training**: `python3 ./experiments/train_s2s.py --mpnn --cuda`
- **Prediction**: `python3 test_redesign.py --mpnn --restore ./log/best_checkpoint_epoch**.pt`

### Model Architecture
The model integrates various features:
- **Featurization Layers**: Handling of protein data into usable features.
- **Embedding Layers**: Transformation layers for node and edge features.
- **Transformer/MPNN Layers**: Encoding and decoding layers for sequence prediction.
- **Output Layer**: Transforms the final states into the probability distribution over amino acids.

### Visualizing Results
We provide scripts to visualize the protein structure predictions using NGLview within Jupyter notebooks, allowing users to assess the quality of predicted structures directly.

### Exporting Data
The project includes utilities to export processed data into JSONL format suitable for input into our models, as well as creating PDB files for visual analysis.

### Conclusion
Our project demonstrates effective generation of MSAs with structures similar to known proteins. Future improvements could include metrics to quantify the closeness of predicted and native protein structures.
