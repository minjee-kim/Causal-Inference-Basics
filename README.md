# Causal Inference

The purpose of this mini project is to review and practice fundamental methods in **causal inference**. <br>

The project will begin with simple simulated examples where the true treatment effect is known, and then move toward an application using observational data. <br>

My personal notes on related concepts and methods are available in `notes.md`. <br>

## Overview

A statistical association between a treatment and an outcome does not necessarily represent a causal effect. In observational data, treatment groups may differ systematically because of baseline characteristics that affect both treatment assignment and the outcome.

The goal of this project is to understand how causal inference methods attempt to account for these differences and estimate treatment effects under explicit assumptions.

Topics of interest include:

- Potential outcomes
- Average treatment effects
- Randomization
- Confounding
- Causal identification assumptions
- Regression adjustment
- Propensity scores
- Covariate balance
- Inverse probability weighting
- Doubly robust estimation
- Connections to Double/Debiased Machine Learning

## Analysis

### 1. Potential outcomes and randomization

Start with the potential outcomes framework:

$$
Y_i(1), \qquad Y_i(0),
$$

where $Y_i(1)$ and $Y_i(0)$ represent the outcomes that would be observed for individual $i$ under treatment and control.

The primary estimand will be the average treatment effect:

$$
ATE = E[Y(1)-Y(0)].
$$

Using simulated data with a known treatment effect, I will first examine why random treatment assignment allows a simple comparison between treatment groups to estimate the causal effect.

### 2. Confounding

The simulation will then be modified so that treatment assignment depends on baseline covariates.

This will allow comparison of:

- randomized treatment assignment,
- confounded treatment assignment, and
- the resulting bias in a naive treatment-control comparison.

The goal is to understand why adjustment is needed when treatment is not randomized.

### 3. Regression adjustment

Regression models will be used to adjust for measured confounders.

The analysis will compare correctly specified and misspecified outcome models to examine how model assumptions affect treatment-effect estimation.

### 4. Propensity scores and inverse probability weighting

The propensity score

$$
e(X)=P(A=1\mid X)
$$

will be estimated using baseline covariates.

I will examine:

- treatment-group overlap,
- propensity-score distributions,
- inverse probability weights, and
- covariate balance before and after weighting.

The resulting treatment-effect estimates will be compared with the known simulation truth.

### 5. Doubly robust estimation

Outcome regression and propensity-score modeling will then be combined using an augmented inverse probability weighted (AIPW) estimator.

This section will examine the idea of **double robustness** and provide a conceptual bridge to my separate project on [Double/Debiased Machine Learning](https://github.com/minjee-kim/Double-Debiased-ML).

### 6. Observational data application

Finally, the methods will be applied to a real observational dataset.

The analysis will include:

1. Defining the causal question and target estimand
2. Identifying treatment, outcome, and baseline confounders
3. Examining treatment-group differences
4. Assessing overlap
5. Estimating propensity scores
6. Evaluating covariate balance
7. Estimating the treatment effect using multiple methods
8. Discussing the assumptions required for a causal interpretation

## Methods

Treatment-effect estimators considered in this project may include:

- Unadjusted difference in means
- Regression adjustment
- Inverse probability weighting
- Augmented inverse probability weighting

The simulated examples will allow the methods to be evaluated using:

- Bias
- Variance
- Root mean squared error
- Confidence interval coverage

## Related Projects

- [A/B Testing and Experimental Design](https://github.com/minjee-kim/ab-testing)
- [Double/Debiased Machine Learning](https://github.com/minjee-kim/Double-Debiased-ML)

## Related Topics

Causal inference, potential outcomes, treatment effects, randomized experiments, observational studies, confounding, propensity scores, covariate balance, inverse probability weighting, doubly robust estimation, experimental design
