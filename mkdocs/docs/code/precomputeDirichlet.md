#### precomputeDirichlet

`precomputeDirichlet(dirichletIndices, uBoundaryFunction, boundaryPositions, wallDistances, theta, tauVector)`

The pre-processing of the Dirichlet boundary condition involves computing the displacement solution at each boundary interception point of all possible links (see [here](implicitGeometryRepresentation.md)). The boundary condition is set up by precomputing the right-hand side source term (`inhomogeneity` in code) and the `momentMatrix` to be applied to the available moments at each boundary node for higher-order corrections.

_Input Arguments_

 - `dirichletIndices` - [_nVelocities,nNodes_] - true if specific link of this node intercepts a Dirichlet boundary

 - `uBoundaryFunction` - function handle for x and y component of the displacement at the Dirichlet boundary

- `boundaryPosition` - [_nVelocities,nNodes,2_] - x and y position of each boundary intersection point for each link and boundary node

 - `wallDistances` - [_nVelocities,nNodes_] - sub-grid wall distance `[0,1]` of each boundary node and link that intercepts the boundary (distance between node and boundary interception point along link, normalized by the link distance)

 - `theta` - dimensionless lattice speed (here always set to 1/3)

 - `tauVector` - vector of all dimensionless relaxation times

_Output Arguments_

 - `distributionMatrix` - determines the linear combination of all post-collision populations at each boundary node to be used for the boundary formulation; for the Dirichlet formulation this is only the outgoing population

 - `momentMatrix` - determines the linear combination of moments available at each boundary node to perform higher-order corrections

 - `inhomogeneity` - source term of the boundary formulation to apply the (inhomogeneous) boundary condition