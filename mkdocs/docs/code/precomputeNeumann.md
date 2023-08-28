####precomputeNeumann

`precomputeNeumann(neumannIndices, streamingMask, tractionBoundaryFunction, bodyLoadFunction, normalBoundaryFunction, boundaryPositions, wallDistances, theta, tauVector, dx, dt, offsetVector)`

The pre-processing of the Neumann boundary condition involves computing the traction at each boundary interception point of all possible links (see [here](implicitGeometryRepresentation.md)). The boundary condition is set up by precomputing the right-hand side source term (`inhomogeneity` in code) and the `momentMatrix` to be applied to the available moments at each boundary node for higher-order corrections. Additionally, potential neighbor nodes inside the domain are determined to perform a finite difference approximation of required quantities that cannot be locally reconstructed. The neighbor node indices and a moment matrix for the linear combination of moments of the neighbor nodes is output as well.

_Input Arguments_

 - `neumannIndices` - [_nVelocities,nNodes_] - true if specific link of this node intercepts a Neumann boundary

 - `streamingMask` - [_nVelocities,nNodes_] - true if neighbor along the given link is inside the domain

 - `tractionBoundaryFunction` - function handle for x and y component of the traction at the Neumann boundary

 - `bodyLoadFunction` - function handle for x and y component of the body load

 - `normalFunction` - function handle for x and y component of the normal vector

- `boundaryPosition` - [_nVelocities,nNodes,2_] - x and y position of each boundary intersection point for each link and boundary node

 - `wallDistances` - [_nVelocities,nNodes_] - sub-grid wall distance `[0,1]` of each boundary node and link that intercepts the boundary (distance between node and boundary interception point along link, normalized by the link distance)

 - `theta` - dimensionless lattice speed (here always set to 1/3)

 - `tauVector` - vector of all dimensionless relaxation times

 - `dx`, `dt` - grid spacing and time step size

 - `offsetVector` - index offset for each streaming direction

_Output Arguments_

 - `distributionMatrix` - determines the linear combination of all post-collision populations at each boundary node to be used for the boundary formulation

 - `momentMatrix` - determines the linear combination of moments available at each boundary node to perform higher-order corrections

 - `inhomogeneity` - source term of the boundary formulation to apply the (inhomogeneous) boundary condition

 - `neighborIndices` - boundary neighbor nodes required for the finite difference stencil

 - `momentNeighborMatrix` - determines the linear combination of moments at the neighbor nodes needed for the finite difference stencil
