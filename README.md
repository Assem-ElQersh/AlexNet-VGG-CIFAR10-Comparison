# AlexNet and VGG Architectures Comparison on CIFAR-10

This repository contains implementations and comparative analysis of AlexNet and VGG architectures trained on the CIFAR-10 dataset. The project explores differences in model design, feature extraction capabilities, and performance metrics across different neural network architectures.

## Project Overview

The goal of this project is to compare and analyze the performance of several CNN architectures:
- AlexNet (adapted for CIFAR-10)
- VGG-16
- VGG-16 with Batch Normalization
- VGG-8 (reduced depth variant)

## Repository Structure

```
├── README.md
├── report/
│   └── alexnet_vgg_cifar10_report.pdf     # Detailed analysis report
├── src/
│   └── implementations.ipynb              # PyTorch implementation code
└── results/
    ├── 5 epochs results/                  # Results from 5-epoch training
    │   ├── results/
    │   │   └── experiment_results.json
    │   └── visualizations/                # Feature maps and training curves
    └── 40 epochs results/                 # Results from 40-epoch training
        ├── results/
        │   └── experiment_results.json    # Performance metrics
        └── visualizations/                # Feature maps and training curves
```

## Key Findings

Based on our 40-epoch training results:

| Model | Parameters | Test Accuracy | Train Accuracy | Avg. Time per Epoch |
|-------|------------|---------------|----------------|---------------------|
| AlexNet | 23,238,474 | 87.81% | 94.14% | 36.09s |
| VGG-16 | 33,638,218 | 10.00% | 9.94% | 47.08s |
| VGG-16 BN | 33,646,666 | 91.94% | 99.43% | 50.20s |
| VGG-8 | 13,119,050 | 88.32% | 93.11% | 37.97s |

## Key Observations

1. **Batch Normalization Impact**: VGG-16 with Batch Normalization significantly outperforms standard VGG-16, achieving the highest test accuracy of 91.94%.

2. **Model Size vs Performance**: The smaller VGG-8 model (13M parameters) achieves comparable performance to AlexNet (23M parameters) while being more efficient.

3. **Training Difficulty**: Standard VGG-16 without batch normalization failed to learn effectively (10% accuracy), highlighting the importance of normalization in deep architectures.

4. **Speed vs Accuracy Tradeoff**: AlexNet has the fastest training time per epoch while VGG-16 BN delivers the highest accuracy but with the slowest training time.

## Dataset

This project uses the CIFAR-10 dataset, which consists of 60,000 32x32 color images across 10 classes:
- airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck

The dataset can be automatically downloaded using the PyTorch or TensorFlow API as shown in the implementation notebook.

## Usage

To run the code:

1. Clone this repository
2. Install dependencies:
   ```
   pip install torch torchvision matplotlib numpy tqdm
   ```
3. Open and run the notebook in `src/implementations.ipynb`

## Future Work

- Implement other modern architectures (ResNet, EfficientNet)
- Apply advanced regularization techniques
- Explore performance on other datasets
- Implement attention mechanisms

## License

This project is licensed under the MIT License - see the [LICENSE](/LICENSE) file for details.
