# BiMamba-GF

BiMamba-GF is a molecular prediction model for interpretable ototoxicity prediction and applicability domain assessment of environmentally relevant chemicals.

## Model architecture

The model combines molecular graph representations with ECFP4 fingerprints:

- **Graph encoding:** Two KAN-GAT layers encode atom and bond features using Fourier-KAN transformations and graph attention.
- **Bidirectional modelling:** A bidirectional Mamba2 module with shared weights processes atomic representations in forward and reverse directions. Mean pooling produces a graph-level representation.
- **Feature fusion:** The graph representation is concatenated with the ECFP4 fingerprint.
- **Prediction:** A two-layer KAN prediction head outputs the probability of ototoxicity.

Integrated gradients support molecular interpretation, and AD-SAL assesses the applicability domain using structural similarity and local activity consistency.
