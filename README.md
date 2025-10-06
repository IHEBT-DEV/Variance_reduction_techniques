# 🎯 Variance Reduction Techniques for Monte Carlo Option Pricing

## 📘 Introduction

Financial markets are inherently uncertain, and investors often seek protection against adverse price movements using **derivative instruments** such as **options**.  
A common hedging strategy involves buying a **call option** on assets one wishes to acquire and a **put option** on those intended for future sale.

Estimating the fair price of an option is essential for both **hedging** and **speculative** purposes. Since the option value depends on the stochastic evolution of the underlying asset, **Monte Carlo simulations** provide a flexible and powerful tool to approximate expected payoffs — particularly when closed-form analytical formulas are unavailable.

In this project, we:

- Model the underlying asset using a **Geometric Brownian Motion (GBM)** process.  
- Estimate European **call** and **put** option prices using **Monte Carlo simulation**.  
- Apply advanced **variance reduction techniques** to improve estimation accuracy:
  - Antithetic Variates  
  - Control Variates  
  - Importance Sampling (fixed and adaptive)
- Use **Stochastic Gradient Descent (SGD)** to optimize the *tilt parameter* in Importance Sampling, further minimizing estimator variance and improving convergence.

---

## 🧭 Project Overview

The notebook systematically explores Monte Carlo simulation and variance reduction in financial modeling.  
It is organized as follows:

1. **Introduction**
2. **Monte Carlo Simulations**
   - Sampling, Mean estimation, LLN, CLT, Confidence Intervals  
   - Monte Carlo principles and error analysis  
   - Example: Estimating π
3. **Simulation of Random Vectors and Stochastic Processes**
   - Multivariate Normal and Correlated Variables  
   - Wiener Process, GBM, Poisson, and Ornstein–Uhlenbeck Processes
4. **Simulation Techniques**
   - Inverse, Transformation, and Rejection Sampling  
   - Simulation of Gaussian vectors and Brownian motion
5. **Variance Reduction Techniques**
   - Antithetic Variates  
   - Control Variates  
   - Importance Sampling  
   - Stratified Sampling  
   - Common Random Numbers (CRN)
6. **Stochastic Gradient Descent (SGD)**
   - Principle, algorithm, and role in optimizing Importance Sampling
7. **Option Pricing**
   - Review of European call and put options  
   - Implementation of pricing via Monte Carlo
8. **Results and Analysis**
   - Comparison of all methods and evaluation of accuracy
9. **Conclusion**

---

## ⚙️ Technical Details

### 🧩 Libraries Used

```python
numpy
scipy
matplotlib
