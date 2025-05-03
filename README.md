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

1. **Accurate Coresets for LVMs**: Including Gaussian Mixture Models (GMMs) and Single Topic Modeling.
2. **Linear Regression**: Implementation of coreset construction for regression problems.
3. **Caratheodory's Algorithm**: Classical implementation for point selection.
4. **Streaming Caratheodory's Algorithm**: Adaptation for streaming data scenarios.
5. **Faster Caratheodory's Algorithm**: Optimized version with improved performance.

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
