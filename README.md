# Accurate Coresets for Latent Variable Models and Regularized Regression

This repository provides the implementation of the algorithms presented in the paper:

**Accurate Coresets for Latent Variable Models and Regularized Regression**  
*Sanskar Ranjan, Supratim Shit*  
[arXiv:2412.20189](https://arxiv.org/abs/2412.20189)

## Overview

Accurate coresets are weighted subsets of the original dataset that ensure a model trained on the coreset achieves the same accuracy as if trained on the full dataset. This work introduces a unified framework for constructing such coresets for:

- **Latent Variable Models (LVMs)**: Including Gaussian Mixture Models (GMMs), Hidden Markov Models (HMMs), and Latent Dirichlet Allocation (LDA).
- **ℓ<sub>p</sub>-Regularized ℓ<sub>p</sub>-Regression**: Generalizing ridge regression to any even-valued p.

Key contributions:

- A general framework using **Kernelization** to map data into high-dimensional spaces while preserving loss functions.
- Algorithms for constructing accurate coresets with sizes dependent on model complexity, not data size.
- Empirical evaluations demonstrating significant data reduction (often <1% of original size) without loss in model performance.

## Algorithms Implemented

1. **Algorithm 1**: Unified framework for constructing accurate coresets via Kernelization.
2. **Algorithm 2**: Accurate coreset construction for Ridge Regression.
3. **Algorithm 3**: Extension to ℓ<sub>p</sub>-Regularized ℓ<sub>p</sub>-Regression for even-valued p.
4. **Algorithm 4**: Accurate coreset construction for Latent Variable Models.

## Repository Structure

```
├── data/
│   └── [Datasets used for experiments]
├── src/
│   ├── kernelization.py
│   ├── ridge_regression.py
│   ├── lp_regression.py
│   └── latent_variable_models.py
├── experiments/
│   └── [Scripts to reproduce experiments]
├── results/
│   └── [Generated results and plots]
├── requirements.txt
└── README.md
```

## Installation

1. **Clone the repository**:

   ```bash
   git clone https://github.com/yourusername/accurate-coresets.git
   cd accurate-coresets
   ```

2. **Create a virtual environment** (optional but recommended):

   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Ridge Regression
To construct an accurate coreset for Ridge Regression:

```bash
python src/ridge_regression.py --input data/your_dataset.csv --lambda 0.1 --output results/ridge_coreset.csv
```

### ℓ<sub>p</sub>-Regularized ℓ<sub>p</sub>-Regression
For even-valued p (e.g., p=4):

```bash
python src/lp_regression.py --input data/your_dataset.csv --p 4 --lambda 0.1 --output results/lp_coreset.csv
```

### Latent Variable Models
For Gaussian Mixture Models:

```bash
python src/latent_variable_models.py --model gmm --input data/your_dataset.csv --components 5 --output results/gmm_coreset.csv
```

Replace `gmm` with `hmm` or `lda` for other models.

## Experimental Results

The paper's experiments demonstrate that the constructed coresets:

- Maintain model accuracy equivalent to training on full datasets.
- Significantly reduce dataset sizes (often to less than 1%).
- Lead to substantial reductions in training time.

Detailed results and plots can be found in the `results/` directory.

## Citation

If you find this work useful, please cite:

```bibtex
@misc{ranjan2024accuratecoresetslatentvariable,
  title={Accurate Coresets for Latent Variable Models and Regularized Regression},
  author={Sanskar Ranjan and Supratim Shit},
  year={2024},
  eprint={2412.20189},
  archivePrefix={arXiv},
  primaryClass={cs.LG},
  url={https://arxiv.org/abs/2412.20189}
}
```

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Contact

For questions or collaborations, please contact:

- Sanskar Ranjan: sanskar21096@iiitd.ac.in
- Supratim Shit: supratim@iiitd.ac.in
