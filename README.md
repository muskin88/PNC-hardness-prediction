# PNC Hardness Prediction

Prediction of Vickers hardness based on the Principle of Maximum Σ-Coherence (PNC).

## Overview

This repository contains:
- Dataset of 256 materials with experimental Vickers hardness, shear modulus, bulk modulus, and estimated bond covalency
- Python implementation of PNC hardness prediction
- Comparison with Tian (2012), Chen (2011), Gao (2003) models, and ML baselines (Random Forest, Gradient Boosting)

## Key Results

| Model | MAE (GPa) |
|-------|-----------|
| **PNC** | **1.84** |
| Gradient Boosting | 2.36 |
| Random Forest | 2.46 |
| Tian (2012) | 4.46 |
| Chen (2011) | 4.45 |
| Gao (2003) | 5.60 |

- 142% improvement over Tian (2012)
- 28% improvement over Gradient Boosting
- Single physical parameter: $G \times C$ (shear modulus × bond covalency)

## Formula

$$H_v = \alpha \cdot \frac{G \times C}{\gamma} + \beta$$

where $\gamma \approx 118.2$, and $\alpha, \beta$ are linear regression coefficients.

## Installation

```bash
pip install -r requirements.txt
