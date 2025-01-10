# Hidden Markov models and Sequential MC methods
Hidden Markov models and Sequential MC methods project, based on the article *Fitting complex population models by combining particle filters with Markov chain Monte Carlo* (2012) by Jonas Knape and Perry de Valpine.

---

## Code Structure

### Core Methodology

The following components of the code were inspired by the R implementation from the original authors, with specific modifications for this project:

- **Normal Mixture Handling**:
  - `mixtureDensity`: Computes the density of a normal mixture.
  - `getPropDensity`: Constructs adaptive proposals based on posterior traces using BIC for component selection.
    - *Modification*: Improved handling of convergence issues during density approximation.

- **Particle Filtering**:
  - `particleFilterLL`: Implements a particle filter to estimate the log-likelihood of parameters.
    - *Modification*: Adjusted resampling for stability and efficient likelihood estimation.

- **Adaptive MCMC**:
  - Adaptive Metropolis-Hastings algorithm for parameter inference, including a random walk phase and an independence phase.
    - *Modification*: Enhanced covariance updates for better adaptation in higher dimensions.

---

### Extensions

This project introduces the following extensions to the original code :

1. **Euler-Maruyama Discretization**
   - Implemented in the `draw_next_N` function for the logistic model (M1), enabling simulation of nonlinear population dynamics.

2. **Additional Models**
   - **Logistic Growth (M1)**: Includes a nonlinear damping term (`b`) in the drift equation.
   - **Exponential Growth (M3)**: Simplifies the parameter set for reduced complexity.

3. **Bayesian Model Comparison**
