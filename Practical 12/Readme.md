# Metropolis Algorithm & Deterministic Model  
**Practical Report**

---

## Aim

To implement the **Metropolis Algorithm** for sampling from a given probability distribution and to compare the results with a **Deterministic Model** for computing statistical quantities.

---

## PART A: Implementation of Metropolis Algorithm

### Question 1  
**What is the Metropolis Algorithm?**

**Answer:**  
The Metropolis Algorithm is a **Markov Chain Monte Carlo (MCMC)** method used to generate samples from a probability distribution when direct sampling is difficult. It constructs a Markov chain whose stationary distribution is the desired target distribution. Over time, samples produced by the algorithm approximate the target distribution.

---

### Question 2  
**What is the target distribution used in this practical?**

**Answer:**  
In this practical, the target distribution is the **Standard Normal Distribution**:

\[
\pi(x) = \frac{1}{\sqrt{2\pi}} e^{-x^2/2}
\]

Since the Metropolis algorithm only requires the distribution up to a proportionality constant, we use:

\[
\pi(x) \propto e^{-x^2/2}
\]

---

### Question 3  
**Write the algorithm for the Metropolis method.**

**Answer:**  

**Algorithm: Metropolis Algorithm**

1. Initialize the starting point \( x_0 \).
2. For each iteration:
   - Propose a candidate point \( x' \) from a symmetric proposal distribution  
     \( q(x'|x_t) = \mathcal{N}(x_t, \sigma^2) \).
   - Compute the acceptance probability:
     \[
     \alpha = \min\left(1,\frac{\pi(x')}{\pi(x_t)}\right)
     \]
   - Accept the proposed point with probability \( \alpha \).
3. Repeat the process for a large number of iterations.
4. Discard initial samples as **burn-in**.
5. The remaining values are samples from the target distribution.

---

### Question 4  
**Explain the code implementation.**

**Answer:**  

- A function `log_target_density(x)` is defined for the logarithm of the target distribution.
- The proposal distribution is a normal random walk.
- Acceptance or rejection is decided using the logarithm of acceptance probability.
- Burn-in samples are discarded to remove initial bias.
- The final samples are used to estimate the mean, variance, and probability density.

---

### Observations (PART A)

- The histogram of samples closely follows the true normal distribution.
- The sample mean is approximately **0**.
- The sample variance is approximately **1**, which matches the theoretical value.
- The acceptance rate depends on the proposal standard deviation.

---

## PART B: Deterministic Model

### Question 5  
**What is meant by a deterministic model?**

**Answer:**  
A deterministic model computes results using **fixed numerical methods** without any randomness. Unlike Monte Carlo methods, deterministic models produce the same output every time for a given input.

---

### Question 6  
**What deterministic approach is used in this practical?**

**Answer:**  
A **numerical integration (grid-based method)** is used to compute statistical quantities of the normal distribution by discretizing the domain and approximating integrals using summation.

---

### Question 7  
**What quantity is computed using the deterministic model?**

**Answer:**  
The expected value of \( X^2 \) under the standard normal distribution:

\[
E[X^2] = \int_{-\infty}^{\infty} x^2 \pi(x)\,dx
\]

The known theoretical value is:

\[
E[X^2] = 1
\]

---

### Question 8  
**Explain the deterministic computation.**

**Answer:**  

1. A fixed grid of x-values is created.
2. The normal probability density function is evaluated on the grid.
3. The density is numerically normalized.
4. The integral is approximated using a weighted sum:
   \[
   E[X^2] \approx \sum x_i^2 \cdot \pi(x_i) \cdot \Delta x
   \]

---

### Comparison of Models

| Method | Estimated Value of E[X²] | Nature |
|------|--------------------------|-------|
| Metropolis Algorithm | ≈ 1.0 | Stochastic |
| Deterministic Model | ≈ 1.0 | Deterministic |
| True Value | 1.0 | Analytical |

---

## Advantages and Limitations

### Metropolis Algorithm
**Advantages**
- Works well in high-dimensional spaces.
- Does not require normalized distributions.

**Limitations**
- Results contain sampling noise.
- Requires tuning of proposal distribution.
- Needs burn-in and convergence checks.

---

### Deterministic Model
**Advantages**
- Simple and exact for low-dimensional problems.
- No randomness involved.

**Limitations**
- Computationally expensive in high dimensions.
- Not feasible for complex, multidimensional distributions.

---

## Conclusion

In this practical:

- The **Metropolis Algorithm** was successfully implemented to sample from a standard normal distribution.
- A **deterministic numerical integration technique** was used to compute expectations analytically.
- Both approaches produced results consistent with the theoretical values.
- The experiment demonstrates the effectiveness of MCMC methods in scenarios where deterministic methods become infeasible.

---

## Result

✅ The Metropolis Algorithm correctly approximates the target distribution.  
✅ The deterministic model verifies the correctness of Monte Carlo estimates.  

---

## References

1. Metropolis et al., *Equation of State Calculations by Fast Computing Machines*, 1953  
2. Robert & Casella, *Monte Carlo Statistical Methods*  
3. Gelman et al., *Bayesian Data Analysis*

---
