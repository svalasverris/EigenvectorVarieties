# Eigenvector Varieties

Numerical computations supporting the paper Eigenvector Varieties, authored by Sandra Di Rocco, Bernd Sturmfels and Svala Sverrisdóttir.

## Notebooks

### [`dimTwoBodyEigenvectorVariety.ipynb`](dimTwoBodyEigenvectorVariety.ipynb)

Computes the dimension of the eigenvector variety for the fermionic two-body operator $W$ acting on $\wedge^{k}ℂ^{m}$. The operator is parametrized by a complex $\binom{m}{2}\times\binom{m}{2}$ symmetric matrix $w$. The dimension equals $\mathrm{rank}(M(x)) - 1$, where $M(x)$ is the Jacobian of the eigenpair equations with respect to the parameters $w$.

### [`degreeLinearDeterminantalLocus.ipynb`](degreeLinearDeterminantalLocus.ipynb)

For generic $ℋ$, the eigenvector variety $ℰ(ℋ)$ is a degree-$n$ hypersurface in $ℙ^{n-1}$ with the $n\times n$ linear determinantal representation

$$f(x_1,\dots,x_n) = \det\bigl[H_1\, x \mid \cdots \mid H_d\, x \mid x\bigr], \qquad H_1,\dots,H_d\in ℂ^{n\times n},\quad d=n-1.$$

Let $ℒ$ denote the locus of generic eigenvector varieties — the Zariski closure of these $f$ inside $ℙ^{\binom{2n-1}{n}-1}$. By Corollary 2.5 in our paper, $\dim ℒ = n^3 - 2n^2 + 1$ for $n\ge 4$. This notebook verifies $\dim ℒ$ numerically and computes $\deg ℒ$ via monodromy in `HomotopyContinuation.jl`.

The default case $(d,n)=(3,4)$ is the locus $ℱ_1$ defined in Leal–Lozano Huerta–Vite ([arXiv:2303.09028](https://arxiv.org/abs/2303.09028)), where it is shown to be an irreducible hypersurface in $ℙ^{34}$ of degree $320{,}112$ (Theorem 2, via intersection theory). The notebook reproduces this number numerically.

## Running

Both notebooks are written for Julia 1.12 with a multi-threaded kernel.  Dependencies:

```julia
using HomotopyContinuation
using LinearAlgebra
using SparseArrays
using Arpack
using Combinatorics
using Base.Threads
```

The monodromy computation in `degreeLinearDeterminantalLocus.ipynb` is slow — running it on a server with >100 threads is recommended.
