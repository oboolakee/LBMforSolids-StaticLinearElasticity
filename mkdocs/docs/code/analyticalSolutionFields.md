#### analyticalSolutionFields

`analyticalSolutionFields(uAnalyticalSym, normalSym, shear, bulk)`

Based on the target manufactured solution, compute all required input data and verification sets and output as function handles. All quantities are expressed in physical (or dimensionless) units.

_Input Arguments_


 - `levelSetFunction` - symbolic expression for geometry definition (using symbolic variables `x` and `y`)

- `normalSym` - symbolic function of the normal vector (using symbolic variables `x` and `y`)

 - `shear`, `bulk` - shear and bulk modulus of the material definition

_Output Arguments_

 - `bodyLoadFunction` - function handle for x and y component of the body load

 - `uBoundaryFunction` - function handle for x and y component of the displacement at the Dirichlet boundary

 - `tractionBoundaryFunction` - function handle for x and y component of the traction at the Neumann boundary

 - `normalFunction` - function handle for x and y component of the normal vector

 - `uDomainFunction` - function handle for x and y component of the displacement solution

 - `sigmaDomainFunction` - function handle for x and y component of the stress solution in Voigt notation [_sigmaxx, sigmayy, sigmaxy_]
