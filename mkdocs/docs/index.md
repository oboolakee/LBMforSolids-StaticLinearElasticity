# Lattice Boltzmann method for solid mechanics

_LBM for solid mechanics_ is a novel lattice Boltzmann formulation to solve solid mechanics problems. This initial contribution considers linear elasticity in 2D in the quasi static limit. The static equilibrium solution is obtained through an iterative procedure in pseudo time. For the static displacement solution second order convergence is achieved on 2D domains with arbitrary boundary geometry and both Dirichlet and Neumann boundary conditions. Details on the derivations are found [here](publications.md).

## Code

Our Matlab test code of the LBM formulation on arbitrary 2D domains is available on [GitHub](https://github.com/oboolakee/LBMforSolids-StaticLinearElasticity). This documentation describes the main concept of each function and explains the input and output arguments.