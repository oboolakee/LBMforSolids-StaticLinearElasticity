#### solve

`solve(refinementFactor)`

Main function calling all pre-processing functions, performing the main iteration loop and post-processing. The input section specifies all _discretization parameters_ and the _problem definiton_:

 - `nxBase` - number of lattice nodes placed along x-direction of bounding box (see below)

 - `timeStepsBase` - number of time steps placed in pseudo time segment

- `refinementFactor` - factor for grid and time step refinement according to diffusive scaling (`<1` for refinement); comment out if input argument is to be applied

 - `E` - Young's modulus

 - `nu` - Poisson's ratio

 - `levelSetFunction` - symbolic expression for geometry definition (using symbolic variables `x` and `y`

 - `neumannGeometryFunction` - symbolic function to define Dirichlet `<=0` and Neumann `>0` portion of boundary

 - `boundingBox` - rectangular simulation domain to be filled with the lattice [_x of left side, x of right side, y of bottom side, y of top side_]

 - `uAnalyticalSim` - symbolic expression of target manufactured solution to be used to generate all data for the body load, boundary conditions and error analysis

_Input Arguments_

- `refinementFactor` - factor for grid and time step refinement according to diffusive scaling

_Output Arguments_

- `dx` - grid spacing as characteristic smallness parameter of the simulation

- `L2ErrorDisp`, `LinfErrorDisp`,`L2ErrorStress`, `LinfErrorStress` - L2/Linf error of the displacement/stress solution at the final time step

- `ELattice` - Young's modulus in lattice units

- `nu` - Poisson's ratio (dimensionless)