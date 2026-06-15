# Eigenvector Varieties

Numerical computations supporting the paper Eigenvector Varieties, authored by Sandra Di Rocco, Bernd Sturmfels and Svala Sverrisdóttir.

## Notebooks

### [`dimTwoBodyEigenvectorVariety.ipynb`](dimTwoBodyEigenvectorVariety.ipynb)

Computes the dimension of the eigenvector variety for the fermionic two-body operator $W$ acting on $\wedge^{k}ℂ^{m}$. The operator is parametrized by a complex $\binom{m}{2}\times\binom{m}{2}$ symmetric matrix $w$. The dimension equals $\mathrm{rank}(M(x)) - 1$, where $M(x)$ is the Jacobian of the eigenpair equations with respect to the parameters $w$.

### [`degreeLinearDeterminantalLocus.ipynb`](degreeLinearDeterminantalLocus.ipynb)

For $(d,n)=(3,4)$ and general $ℋ$, the eigenvector variety $ℰ(ℋ)$ is a quartic surface in $ℙ^{3}$ with a $4\times 4$ linear determinantal representation

$$f(x,y,z,w) = \det\bigl[A X \mid B X \mid C X \mid X\bigr], \qquad A,B,C\in ℂ^{4\times 4}.$$

This notebook numerically verifies, via monodromy in `HomotopyContinuation.jl`, that the locus of such quartics is an irreducible hypersurface in $ℙ^{34}$ of degree $320{,}112$. This value was first obtained in Leal–Lozano Huerta–Vite ([arXiv:2303.09028](https://arxiv.org/abs/2303.09028), Theorem 2) via intersection theory.

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
