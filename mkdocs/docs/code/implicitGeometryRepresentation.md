#### implicitGeometryRepresentation

`implicitGeometryRepresentation(levelSetFunction, neumannFunction, lattice)`

Determines the nodes inside the domain, the nodes next to the boundary and sub-grid wall distances of all links intercepting the boundary using a line search algorithm. For the Neumann boundary portion, the normal vector orientation is also determined.

_Input Arguments_


 - `levelSetFunction` - symbolic expression for geometry definition (using symbolic variables `x` and `y`)

 - `neumannGeometryFunction` - symbolic function to define Dirichlet `<=0` and Neumann `>0` portion of boundary

- `grid` - output of `gridGeneration()` [_x of first node on the left, x of last node on the right, number of nodes in x direction; y of first node at the bottom, y of last node on the top, number of nodes in y direction_]

_Output Arguments_

The shape of the output data is also specified using the total number of lattice nodes `nNodes`, number of domain nodes `nDomainNodes` and number of lattice velocities `nVelocities` (the code always assumes the D2Q8 stencil)

 - `domainIndices` - [_1,nNodes_] - true/false if node is inside the domain

 - `domainPositions` - [_2,nDomainNodes_] - x and y position off all nodes inside the domain

 - `streamingIndices` - cell array of node indeces of all available domain nodes for each streaming direction

 - `dirichletIndices` - [_nVelocities,nNodes_] - true if specific link of this node intercepts a Dirichlet boundary

 - `neumannIndices` - [_nVelocities,nNodes_] - true if specific link of this node intercepts a Neumann boundary

 - `wallDistances` - [_nVelocities,nNodes_] - sub-grid wall distance `[0,1]` of each boundary node and link that intercepts the boundary (distance between node and boundary interception point along link, normalized by the link distance)

- `boundaryPosition` - [_nVelocities,nNodes,2_] - x and y position of each boundary intersection point for each link and boundary node

- `normalSym` - symbolic function of the normal vector

 - `streamingMask` - [_nVelocities,nNodes_] - true if neighbor along the given link is inside the domain
