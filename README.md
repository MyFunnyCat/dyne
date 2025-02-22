![tests status](https://github.com/nmayorov/dyne/actions/workflows/build_and_test.yaml/badge.svg)

# dyne

dyne is a Python package containing a collection of algorithms for state estimation in dynamic 
systems.
Specifically it deals with discrete-time stochastic dynamic systems of the form:

```math
\begin{gather}
X_{k + 1} = f_k(X_k, W_k) \\
Z_{k} = h_k(X_k) + V_k
\end{gather}
```
With

- $k$ - integer epoch index
- $X_k$ - state vector
- $W_k$ - process noise vector
- $Z_k$ - measurement vector
- $V_k$ - measurement noise vector
- $f_k$ - process function
- $h_k$ - measurement function

The task is to estimate $X_k$ given the known process dynamics and measurements.

At the moment the following algorithms are implemented in `dyne`:

- Linear Kalman filter and smoother
- Extended Kalman Filter
- Unscented Kalman Filter
- Moving Horizon Filter (windowed nonlinear optimization, backward-smoothing EKF)
- Full nonlinear batch optimization (optimal nonlinear smoother)

## Installation

The package is pure Python and can be easily installed on any platform.
Runtime dependencies include (versions in parentheses were used for the latest development):

* numpy (1.25.2)
* scipy (1.11.3)

To perform a regular install, execute in the cloned repository directory: 
```shell
pip install .
```
To perform an editable (inplace) install:
```shell
pip install -e .
```
