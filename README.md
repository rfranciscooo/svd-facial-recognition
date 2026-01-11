# Facial Recognition with Linear Systems

This repository contains a technical research project exploring facial recognition using linear algebra, with a focus on Singular Value Decomposition (SVD) and projection-based classification. The project demonstrates how high-dimensional image data can be modeled using linear systems to analyze and distinguish facial expressions associated with different human emotions.

This work was developed as a technical report for an undergraduate course.

---

## Research Overview

The objective of this project is to evaluate how effectively SVD-based subspace models can capture and distinguish facial expressions. Facial images are represented as high-dimensional vectors and grouped into emotion-specific matrices. Each emotion is modeled by a low-dimensional orthonormal basis obtained via SVD.

New images are classified by projecting them onto each emotion subspace and comparing residual norms, with smaller residuals indicating closer alignment with the corresponding emotional model.

---

## Key Concepts

- Singular Value Decomposition (SVD)
- Orthonormal bases and low-rank approximations
- Projection matrices
- High-dimensional image representation
- Residual-based classification
- Train/test data splitting

---

## Mathematical Framework

For each emotion matrix A_i:

1. Compute the Singular Value Decomposition:
   A_i = U_i Σ_i V_i^T

2. Use the leading columns of U_i to form a low-dimensional orthonormal basis.

3. Construct the projection matrix:
   P_i = U_i U_i^T

4. For a test image vector v, compute the residual:
   r = || (I − P_i) v ||

The emotion corresponding to the smallest average residual across test images is considered the best-fit model.

All image data are mean-centered prior to decomposition so that SVD captures structural facial variation rather than average facial geometry.

---

## Data

- Source: Kaggle facial expression dataset
- Format: Grayscale PNG images
- Emotions analyzed:
  - Anger
  - Contempt
  - Disgust
  - Fear
  - Happiness
  - Sadness
  - Surprise

Each emotion class contains a different number of images, resulting in matrices of varying dimensions.

---

## Methods Summary

- Approach: Linear subspace classification
- Core method: Singular Value Decomposition
- Preprocessing: Image vectorization and mean-centering
- Evaluation: Train/test split with residual norm comparison
- Implementation language: R

---

## Results Summary

Results indicate that certain emotions—particularly Contempt, Disgust, and Anger—exhibit lower projection residuals, suggesting less variability in facial representation within those categories in the available dataset.

These findings highlight the effectiveness of SVD in capturing dominant structural features in image-based data.

---

## Author Contribution

This project was completed collaboratively. Contributions are summarized as follows:

- Roger Carranza Aronne
  - Full written report
  - Developed the LaTeX document and final presentation
  - Contributed to methodology design
  - Interpreted results and synthesized conclusions


The project methodology was designed jointly by the primary contributors. The written exposition and final presentation were led by Roger Carranza Aronne.

---

## Authors

- Roger Carranza Aronne
- David Trinh
- Jefferson Cunin

---

## Context

This project was completed as Technical Report for MATH 365: Computational Linear Algebra at Macalester College (Spring 2025). It serves as both a mathematical exposition of Singular Value Decomposition and a practical application of linear algebra to image-based pattern recognition.

---

## References

- Kaggle Facial Expression Dataset
- Course materials on Singular Value Decomposition and projection matrices
- R magick package documentation for image processing
