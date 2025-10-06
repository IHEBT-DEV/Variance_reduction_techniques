# Variance Reduction Techniques in Monte Carlo Simulations for Option Pricing

## 🧠 Introduction

To hedge against market movements that could be unfavorable, an investor can buy a **call option** on the securities they wish to acquire and a **put option** on those they intend to sell in the future.  

To assess the price of the option (call or put), which depends on the future values of the underlying asset, we must first **model the asset’s evolution** and then **estimate the option price**.  

In this project, we employ **Monte Carlo simulations** using the **Geometric Brownian Motion (GBM)** model to simulate underlying asset prices.  
To improve the precision of our estimates, we use **variance reduction techniques** such as:
- Antithetic Variates  
- Control Variates  
- Importance Sampling  

Additionally, a **Stochastic Gradient Descent (SGD)** algorithm is used to optimize the importance sampling tilt parameter, enhancing convergence and accuracy.

---

## 📘 Project Structure & Plan

1. **Introduction**  
2. **Monte Carlo Simulations**  
   - Sampling  
   - Mean Estimation  
   - Law of Large Numbers  
   - Central Limit Theorem  
   - Confidence Intervals  
3. **Simulation of Random Vectors and Stochastic Processes**  
   - Random Variables  
   - Multivariate Normal Distribution  
   - Brownian Motion & Geometric Brownian Motion  
4. **Variance Reduction Techniques**  
   - Antithetic Variates  
   - Control Variates  
   - Importance Sampling  
   - Stratified Sampling  
   - Common Random Numbers (CRN)  
5. **Stochastic Gradient Algorithm**  
   - Principle  
   - Implementation  
   - Advantages and Limitations  
6. **Option Contracts**  
   - Call and Put Options  
   - European Option Pricing Practice  
7. **Results Analysis and Conclusion**

---

## 📊 Simulation Parameters

| Parameter | Symbol | Value | Description |
|------------|---------|--------|-------------|
| Number of simulations for call option | n | 50,000 | Monte Carlo iterations |
| Number of simulations for put option | n | 10,000 | Monte Carlo iterations |
| Underlying asset price | S₀ | 100 | Initial asset price |
| Time to maturity | T | 1 year | Simulation horizon |
| Volatility | σ | 1 | Annual volatility |
| Strike price | K | 100 | Option strike |
| Risk-free rate | r | 0.05 | Constant risk-free interest rate |
| Number of steps | 252 | — | Daily time steps |
| SGD iterations | — | 100 | Optimization loop |
| Learning rate | η | 0.01 | SGD learning rate |

---

## 📈 Results and Comparison

### 🟦 Call Option Pricing

| Method | Price Estimate | Theoretical Price (Black–Scholes) | Max Weight | Min Weight | Notes |
|--------|----------------|------------------------------------|-------------|-------------|--------|
| **Theoretical (Black–Scholes)** | 10.4506 | 10.4506 | - | - | The exact theoretical price calculated using the Black–Scholes formula. |
| **Classic Monte Carlo** | 10.3412 | 10.4506 | - | - | Standard Monte Carlo method without variance reduction. |
| **Antithetic Variates** | 10.4214 | 10.4506 | - | - | Uses antithetic paths for variance reduction. |
| **Control Variates** | 10.4401 | 10.4506 | - | - | Uses Black–Scholes as a control variate to reduce variance. |
| **Importance Sampling (fixed θ)** | 10.4450 | 10.4506 | - | - | Importance sampling with a fixed tilt parameter. |
| **Importance Sampling (SGD optimized)** | 10.4462 | 10.4506 | Max: 1.35 | Min: 0.13 | Optimized tilt parameter θ using SGD. |

---

### 🟥 Put Option Pricing

| Method | Estimated Price | Theoretical Price (Black–Scholes) | Max Weight | Min Weight | Notes |
|--------|-----------------|------------------------------------|-------------|-------------|--------|
| **Classic Monte Carlo** | 5.38 | 5.382 | N/A | N/A | No variance reduction. Results are close to theoretical price. |
| **Antithetic Variates** | 5.66 | 5.382 | N/A | N/A | Slight increase in price estimate. Helps reduce variance. |
| **Control Variates** | 5.55 | 5.382 | N/A | N/A | Control variate technique reduces variance but still close to theoretical price. |
| **Importance Sampling (fixed θ = 0.005)** | 5.78 | 5.382 | 1.35 | 0.51 | Uses a fixed tilt parameter, with reduced variance. |
| **Importance Sampling (SGD-optimized θ)** | 5.72 | 5.382 | 1.50 | 0.30 | SGD optimization further improves variance reduction. |

---
# ⚙️ Technical Details

## 🚀 How to Run the Notebook

1. Clone this repository:
   ```bash
   git clone https://github.com/IHEBT-DEV/Variance_reduction_techniques.git
   ```
2. Open the notebook in [Google Colab](https://colab.research.google.com/).
3. Run all cells sequentially to reproduce the results.
4. (Optional) Modify parameters such as `n`, `σ`, or `r` to experiment with different scenarios.

---

## 📂 Repository Structure

```
Variance_reduction_techniques/
│
├── Variance_reduction_techniques_with_Monte_Carlo.ipynb   # Main Google Colab notebook
└──── README.md                                              # Project documentation
```

---

## 🧩Technologies and Libraries Used

- **Python**
- **NumPy**
- **SciPy**
- **Matplotlib**
---

## 🧩 Key Insights

- Variance reduction significantly improves Monte Carlo efficiency.  
- Antithetic and control variates provide consistent gains with minimal complexity.  
- Importance sampling — particularly with **SGD-optimized parameters** — achieves near-theoretical precision.  
- Theoretical and simulated prices align closely, validating all techniques.

---

## ✨ Future Improvements

- Extend to **American options** using Longstaff–Schwartz regression.  
- Compare with **Quasi-Monte Carlo** methods (Sobol, Halton sequences).  
- Integrate **GPU acceleration** for faster convergence.  
- Implement **adaptive learning rate** for SGD optimization.

---


## 🧑‍💻 Author

**Iheb T**  
Quantitative Developer & Research Enthusiast  
Focused on simulation methods, stochastic modeling, and quantitative finance
📂 GitHub: [IHEBT-DEV](https://github.com/IHEBT-DEV)  
💼 LinkedIn: [linkedin.com/in/iheb-touati](https://linkedin.com/in/iheb-touati)

---

## 📄 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

---
> _"In quantitative finance, variance is inevitable — but unnecessary variance is not."_





