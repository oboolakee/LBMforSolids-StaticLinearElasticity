#### gridGeneration

`gridGeneration(boundingBox, levelSetFunction, nx)`

Adjust the bounding box limits so that the geometry defined by the level set function is containend inside and output min/max coordinates of lattice nodes and number of nodes in each direction. The resulting lattice is the smallest rectangle that contains the geometry + one ghost node layer on each side. However, the user must ensure that the input geometry is fully contained inside the `boundingBox`!

_Input Arguments_

 - `boundingBox` - rectangular simulation domain to be filled with the lattice [_x of left side, x of right side, y of bottom side, y of top side_]

 - `levelSetFunction` - symbolic expression for geometry definition (using symbolic variables `x` and `y`

 - `nx` - number of lattice nodes along x-direction of bounding box (with potential refinement applied)

_Output Arguments_

- `lattice` - [_x of first node on the left, x of last node on the right, number of nodes in x direction; y of first node at the bottom, y of last node on the top, number of nodes in y direction_]