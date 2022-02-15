# Correlation/Covariance Matrix

## Definition

* **Correlation** is a statistical relationship between two random variables. The **correlation matrix** of $$n$$ random variables $$X_1, \ldots, X_n$$ is the $$n \times n$$ matrix whose $$(i,j)$$ entry is $$corr(X_i,X_j)$$. Thus the diagonal entries are all identically unity, i.e. 1.
* **Covariance** is a measure of the joint variability of two random variables, in other words, the directional relationship. The **covariance matrix** of $$n$$ random variables $$X_1, \ldots, X_n$$ is the $$n \times n$$ matrix whose $$(i,j)$$ entry is $$cov(X_i,X_j)$$. Thus the diagonal entries are variance of $$X_i$$.

## Calculation

The most common measure of the correation is the Pearson's correlation coefficient. It is obtained by taking the ratio of the covarience of the two variables to the square root of their variances.

$$
\rho_{X,Y} =corr(X,Y) = {cov(X,Y) \over {\sigma_X \sigma_Y}}={E[(X-\mu_X)(Y-\mu_Y)] \over {\sigma_X \sigma_Y}}
$$

Correlation matrix is&#x20;

$$
R=\begin{bmatrix}
\rho_{11} & \cdots & \rho_{1n}\\ 
\vdots &  & \vdots \\ 
\rho_{n1} & \cdots  & \rho_{nn}
\end{bmatrix}
$$

Covariance matrix is

$$
V = \begin{bmatrix}
\sigma_{11} & \cdots & \sigma_{1n}\\ 
\vdots &  & \vdots \\ 
\sigma_{n1} & \cdots  & \sigma_{nn}
\end{bmatrix}
$$

The conversion between them is

$$
\begin{align*}
D &= Diag(\sigma_i) \\
V &= D \cdot R \cdot D \\
R &= inv(D) \cdot V \cdot inv(D)
\end{align*}
$$

### Fixing Correlation / Covariance matrix

The correlation / covariance matrix is calculated using historical data and pairwise, and then put into the form of a symmetric matrix. For jointly normal random variables, this single number summarizes all there is to know about the relationship between the two.

In ideal cases, where observations are complete, we can produce the correlation / covariance matrix with by using the observed sample. However, the real world data poses several challenges.&#x20;

* Data might not exist till recent one year, or
* poor quality when contract was still undergoing acceptance by the communication, or
* outliers due to market stress event.

There is no guarantee that this matrix satisfies that it is a positive definite matrix to enable decomposition. We may employ below procedure:

1. Try eigen decomposition of the matrix, setting any negative eigenvalues to zero, and then reconstructing the resulting matrix.
2. Update the "fixed" matrix such that it is the closest to the original matrix (\[1], \[2]).

### Reference

\[1] Nicholas J. Higham [https://nhigham.com/2013/02/13/the-nearest-correlation-matrix/](https://nhigham.com/2013/02/13/the-nearest-correlation-matrix/)

\[2] Craig Lucas, Computing Nearest Covariance and Correlation Matrices, M.Sc. Thesis, University of Manchester, 2001.













