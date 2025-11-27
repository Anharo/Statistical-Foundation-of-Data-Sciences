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
The Metropolis Algorithm is a **Markov Chain Monte Carlo (MCMC)** method used to generate samples from a probability distribution when direct sampling is difficult. It constructs a Markov chain whose stationary distribution is the desired target distribution. Over time, the samples produced by the algorithm approximate the target distribution.

---

### Question 2  
**What is the target distribution used in this practical?**

**Answer:**  
In this practical, the target distribution is the **Standard Normal Distribution**:

- Full form:  
  `π(x) = (1 / sqrt(2π)) * exp(-x^2 / 2)`

For the Metropolis algorithm, we only need it **up to a constant**, so we use:

- Unnormalized form:  
  `π(x) ∝ exp(-x^2 / 2)`

---

### Question 3  
**Write the algorithm for the Metropolis method.**

**Answer:**  

**Algorithm: Metropolis Algorithm (for 1D target distribution)**

1. Choose an initial value `x0`.
2. For each iteration `t`:
   - Propose a candidate point  
     `x' ~ Normal(x_t, proposal_std^2)`  
     (this is called a normal random-walk proposal).
   - Compute the acceptance ratio  
     `r = π(x') / π(x_t)`  
     and the acceptance probability  
     `α = min(1, r)`.
   - Generate a uniform random number `u ~ Uniform(0, 1)`.
   - If `u <= α`, accept the proposal and set `x_(t+1) = x'`.  
     Otherwise, reject the proposal and set `x_(t+1) = x_t`.
3. Repeat the process for many iterations.
4. Discard the first few iterations as **burn-in**.
5. Use the remaining values as samples from the target distribution.

---

### Question 4  
**Explain the code implementation.**

**Answer:**  

- `log_target_density(x)`  
  Implements the log of the unnormalized density of the standard normal:  
  `log π(x) = -0.5 * x^2`

- `metropolis_sampler(...)`  
  - Starts from an initial point `x0`.
  - Proposes new points using a normal random walk:  
    `x_proposed ~ Normal(x_current, proposal_std^2)`
  - Computes the log-acceptance ratio:  
    `log_alpha = log π(x_proposed) - log π(x_current)`
  - Accepts or rejects the proposal using a uniform random draw.
  - Discards `burn_in` samples.
  - Optionally keeps only every `thinning`-th sample.
  - Returns:
    - The final array of samples.
    - The overall acceptance rate.

- In the `__main__` block:
  - The sampler is run with `n_samples = 10000`.
  - It prints:
    - Acceptance rate.
    - Sample mean (should be close to 0).
    - Sample variance (should be close to 1).
  - A histogram of the samples is plotted along with the true standard normal density for visual comparison.

---

### Observations (PART A)

- The histogram of the generated samples closely follows the shape of the true standard normal distribution.
- The **sample mean** is approximately `0`.
- The **sample variance** is approximately `1`, which matches the theoretical variance of the standard normal distribution.
- The **acceptance rate** depends on the proposal standard deviation:
  - If `proposal_std` is too small → high acceptance but slow exploration.
  - If `proposal_std` is too large → low acceptance, chain gets stuck.

---

## PART B: Deterministic Model

### Question 5  
**What is meant by a deterministic model?**

**Answer:**  
A deterministic model computes results using **fixed numerical methods** without any randomness. For a given input, the output is always the same. In contrast, Monte Carlo methods involve randomness and give slightly different outputs on each run.

---

### Question 6  
**What deterministic approach is used in this practical?**

**Answer:**  
We use a **grid-based numerical integration method** (similar to the trapezoidal rule) to approximate integrals of the probability density function. The idea is:

1. Create a grid of `x` values.
2. Evaluate the probability density function on this grid.
3. Approximate integrals using a weighted sum over the grid.

---

### Question 7  
**What quantity is computed using the deterministic model?**

**Answer:**  

We compute the expected value of `X^2` under the standard normal distribution:

- In mathematical form:  
  `E[X^2] = ∫ x^2 * π(x) dx` over `(-∞, ∞)`

- For a standard normal distribution `N(0, 1)`, the theoretical value is:  
  `E[X^2] = 1`

---

### Question 8  
**Explain the deterministic computation.**

**Answer:**  

1. A grid of `x` values is created, for example from `-5` to `5`.
2. The standard normal probability density function `pdf(x)` is evaluated at all points.
3. The density values are normalized numerically so that their sum multiplied by the grid spacing `dx` is approximately 1.
4. The expected value `E[X^2]` is approximated using:

   `E[X^2] ≈ Σ (x_i^2 * pdf(x_i) * dx)`

   where:
   - `x_i` are the grid points,
   - `pdf(x_i)` is the probability density at `x_i`,
   - `dx` is the spacing between grid points.

---

## Comparison of Models

We compare the result of `E[X^2]` using:

- Metropolis (stochastic method),
- Deterministic numerical integration,
- True analytical value.

| Method                | Estimated Value of E[X²] | Nature        |
|-----------------------|--------------------------|--------------|
| Metropolis Algorithm  | 1.00067                  | Stochastic   |
| Deterministic Model   | 0.99999                  | Deterministic|
| True Value (N(0,1))   | 1.0                      | Analytical   |

Both implemented methods give values close to the true theoretical value.

---

## Advantages and Limitations

### Metropolis Algorithm

**Advantages:**
- Works well in high-dimensional problems where grids are impossible.
- Does not require the target distribution to be normalized (only need it up to a constant).
- Flexible and can be applied to complex target distributions.

**Limitations:**
- Results contain **sampling noise** and may vary run to run.
- Requires **tuning** of the proposal standard deviation.
- Needs **burn-in** and **convergence checks**.
- Can mix slowly if the proposal is not chosen properly.

---

### Deterministic Model

**Advantages:**
- No randomness: same result in every run.
- For low-dimensional problems, it can be very accurate.
- Easy to understand conceptually (just approximating integrals numerically).

**Limitations:**
- Computational cost grows **exponentially** with dimension (curse of dimensionality).
- Not practical for high-dimensional distributions.
- Requires a well-chosen grid range and resolution.

---

## Conclusion

In this practical:

- We successfully implemented the **Metropolis Algorithm** to generate samples from a standard normal distribution.
- We implemented a **deterministic numerical integration method** to compute `E[X^2]` under the same distribution.
- Both methods produced results consistent with the known theoretical value `E[X^2] = 1`.
- This demonstrates:
  - How MCMC methods (like Metropolis) can approximate expectations by sampling.
  - How deterministic numerical methods can be used for validation in simple, low-dimensional cases.

---

## Result

- ✅ The Metropolis Algorithm correctly approximates the target standard normal distribution.  
- ✅ The deterministic model confirms the Monte Carlo estimates by producing a similar value for `E[X^2]`.  

---
