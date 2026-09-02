# Day 13 – Classical Baseline and Edge Metrics

##  Objective

The objective of Day 13 was to implement classical underwater image enhancement methods and evaluate their performance.

Main tasks:
- Implement 2–3 classical enhancement methods.
- Generate enhanced images.
- Compare enhanced images with target images.
- Calculate PSNR and SSIM.
- Extract image edges.
- Measure edge preservation.
- Compare the classical methods.
- Select a strong classical reference.

##  Dataset Used

The experiments used Prepared Dataset V1.

- Total valid input-target pairs: 312
- Training pairs: 218
- Validation pairs: 47
- Testing pairs: 47
- Image size: 256 × 256 pixels
- Image format: PNG
- Color format: RGB

The classical baseline evaluation was performed using the available training input-target pairs.

##  Classical Enhancement Methods

Three classical enhancement methods were implemented:

1. CLAHE
2. Gamma Correction
3. White Balance

### 1 CLAHE

CLAHE (Contrast Limited Adaptive Histogram Equalization) was used to improve local contrast and image visibility.

### 2 Gamma Correction

Gamma Correction was used to adjust image brightness using a nonlinear intensity transformation.

### 3 White Balance

White Balance was used to improve color balance and reduce color cast in underwater images.

##  Enhancement Workflow

Input Image → Classical Enhancement → Enhanced Image → Compare with Target

The three methods were applied separately:

- Input → CLAHE
- Input → Gamma Correction
- Input → White Balance

The enhanced images were saved in separate folders.

##  Visual Comparison

Representative images were visually compared between:

- Input
- Target
- CLAHE
- Gamma Correction
- White Balance

The visual inspection showed that CLAHE provided a stronger visibility improvement compared with the other tested methods.

Gamma Correction provided some brightness improvement, while White Balance produced comparatively smaller changes in the inspected sample.

##  Image Quality Metrics

Two image-quality metrics were used:

- PSNR
- SSIM

### PSNR

PSNR (Peak Signal-to-Noise Ratio) measures pixel-level similarity between the enhanced image and the target image.

A higher PSNR indicates greater similarity to the target.

### SSIM

SSIM (Structural Similarity Index) measures structural similarity between the enhanced image and the target image.

A higher SSIM indicates better structural similarity.

## 7. PSNR and SSIM Results

| Method | PSNR | SSIM |
|---|---:|---:|
| CLAHE | 10.99 | 0.4346 |
| Gamma Correction | 10.93 | 0.4821 |
| White Balance | 10.44 | 0.4611 |

### Observation

CLAHE achieved the highest PSNR value of 10.99.

Gamma Correction achieved the highest SSIM value of 0.4821.

White Balance produced the lowest PSNR value of 10.44.

##  Edge Extraction

Edge extraction was performed using the Canny edge detector.

The purpose was to measure how well important image edges were preserved after enhancement.

Process:

Enhanced Image → Grayscale Conversion → Canny Edge Detection → Detected Edges → Compare with Target Edges

##  Edge Preservation Metric

Edge F1 score was used to compare the edges of the enhanced images with the target images.

A higher Edge F1 score indicates better edge preservation.

##  Edge Preservation Results

| Method | Edge F1 |
|---|---:|
| CLAHE | 0.0572 |
| Gamma Correction | 0.0416 |
| White Balance | 0.0416 |

CLAHE achieved the highest Edge F1 score of 0.0572.

##  Complete Comparison

| Method | PSNR | SSIM | Edge F1 |
|---|---:|---:|---:|
| CLAHE | 10.99 | 0.4346 | 0.0572 |
| Gamma Correction | 10.93 | 0.4821 | 0.0416 |
| White Balance | 10.44 | 0.4611 | 0.0416 |

## 12. Result Analysis

### CLAHE

CLAHE achieved:

- PSNR: 10.99
- SSIM: 0.4346
- Edge F1: 0.0572

It achieved the highest PSNR and Edge F1 among the three methods.

### Gamma Correction

Gamma Correction achieved:

- PSNR: 10.93
- SSIM: 0.4821
- Edge F1: 0.0416

It achieved the highest SSIM among the tested methods.

### White Balance

White Balance achieved:

- PSNR: 10.44
- SSIM: 0.4611
- Edge F1: 0.0416

It showed lower PSNR and edge preservation compared with CLAHE.

##  Selected Classical Reference

Based on the combined evaluation results, CLAHE was selected as the strong classical reference baseline.

Reasons:

- Highest PSNR
- Highest Edge F1
- Strong visual improvement
- Good overall performance compared with the other classical methods

Gamma Correction remains an important comparison because it achieved the highest SSIM.

##  Day 13 Workflow

```text
Dataset V1
↓
Input Images
↓
Classical Enhancement
↓
CLAHE / Gamma Correction / White Balance
↓
Enhanced Images
↓
PSNR + SSIM
↓
Canny Edge Extraction
↓
Edge F1
↓
Method Comparison
↓
Select Classical Reference
↓
CLAHE
```

##  Key Findings

The classical enhancement experiments showed that different methods perform differently depending on the evaluation metric.

- CLAHE achieved the highest PSNR.
- Gamma Correction achieved the highest SSIM.
- CLAHE achieved the highest Edge F1.
- White Balance achieved the lowest PSNR.
- CLAHE provided the strongest overall classical baseline performance.

##  Deliverable

The Day 13 deliverable is:

Classical baseline notebook; edge metrics

The notebook includes:

- Classical enhancement implementation
- CLAHE
- Gamma Correction
- White Balance
- Visual comparison
- PSNR calculation
- SSIM calculation
- Canny edge extraction
- Edge F1 measurement
- Baseline comparison
- Classical reference selection

##  Submission Files

- Underwater_image_Enhancement.ipynb
- classical_results/clahe/
- classical_results/gamma/
- classical_results/white_balance/
- README.md

##  Conclusion

Three classical underwater image enhancement methods were implemented and evaluated.

PSNR, SSIM, and Edge F1 were used to compare their performance.

CLAHE achieved the highest PSNR and Edge F1 values, while Gamma Correction achieved the highest SSIM.

Based on the combined results, CLAHE was selected as the strong classical reference baseline for comparison with future learning-based methods.
