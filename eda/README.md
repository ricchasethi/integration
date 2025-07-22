* Exploratory Data Analysis
Different algorithms for EDA useful in deep neural networks.
1. Autoencoders
- It contains two parts:
  - Encoder: Compresses input into a smaller, dense representation (latent space)
  - Decoder: Reconstructs the original input from that compressed representation.
- Different types of autoencoders:
  - Sparse autoencoders: Encourages sparsity in latent/hidden layer by adding sparsity constraint on activation function.
    - It penalizes non-sparse (i.e. highly active) neurons.
    - Learns more meaningful representation of data even when you have more hidden units than inputs.
    - Would be useful in bioinformatics when biological data is high dimensional (thousands of genes/SNPs), noisy and sparse, unlabeled, cell-type-specific expression patterns (clustering cancer subtypes using learned features instead of raw gene expression), in biomarker discovery (select small subset of SNPs/genes associated with disease), epigenomics (find specific regions where methylation patterns changes).
    - Disadv: It can end up with correlated features (both in input features and latent features). If input has highly correlated features (eg co-expressed genes), sparse autoencoder may select multiple redundant features. To reduce this we can use two approaches: orthogonal penalties or decorrelation losses (sparse filtering, InfoMax, ICA-inspired methods) or concrete autoencoders or L1-regularised models
  - Concrete autoencoders