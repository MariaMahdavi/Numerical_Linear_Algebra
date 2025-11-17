# Natural Gradient Descent — Numerical Linear Algebra Project

This repository contains my final project for the *Numerical Linear Algebra* course, focusing on the **Natural Gradient Descent (NGD)** algorithm.  
The project investigates how NGD behaves compared to classical optimization methods and analyzes the role of ill-conditioned Hessian matrices in convergence and numerical stability.

---

## Overview

The goal of this project is to study optimization methods through the lens of numerical linear algebra.  
Specifically, the project:

- Analyzes the **Natural Gradient Descent (NGD)** method theoretically and numerically.  
- Compares NGD with:
  - **Steepest Descent**
  - **Conjugate Gradient (CG)**
- Examines the effect of **ill-conditioned Hessian matrices** on convergence and stability.  
- Implements all algorithms **from scratch in Python**, without high-level optimization libraries.

---

## Mathematical Background

We consider optimization problems of the form:

\[
\min_x \ \frac{1}{2}x^\top H x - b^\top x
\]

where:

- \( H \) is a symmetric positive-definite Hessian (possibly ill-conditioned)
- \( b \) is the gradient vector

NGD modifies the gradient direction using a Riemannian metric:

\[
x_{k+1} = x_k - \alpha H^{-1} \nabla f(x_k)
\]

This adjustment often results in faster and more stable convergence than Euclidean gradient descent.

---

## Experiments

### Convergence Comparison
- Steepest Descent  
- Conjugate Gradient  
- Natural Gradient Descent  

Metrics measured:
- Number of iterations  
- Error decay  
- Sensitivity to step size  
- Effect of extreme condition numbers  

### Ill-Conditioning Analysis
- Tested Hessians with condition numbers: \( \kappa(H) = 10^2, 10^4, 10^6 \)  
- Evaluated impact on convergence rate, stability, and floating-point behavior  

---

## Results

Key observations:

- NGD is more robust under severe ill-conditioning.  
- Steepest Descent slows significantly as \(\kappa(H)\) increases.  
- Conjugate Gradient performs well but can deteriorate under extreme conditioning.  
- NGD maintains stable convergence due to the geometry-aware metric.

*(Optional: Add plots or figures here to illustrate results)*

---

## Implementation

All algorithms are implemented manually in Python:

- **No use of** `scipy.optimize` or similar high-level solvers  
- **Matrix operations:** NumPy  
- **Visualization:** Matplotlib (optional)  

