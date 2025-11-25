# r.solute.transport

**Category**: raster

## Description

Numerical calculation program for transient, confined and unconfined solute transport in two dimensions

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_solute_transport(c,phead,hc_x,hc_y,status,diff_x,diff_y,q=None,cin=None,cs,rd,nf,top,bottom,output,vx=None,vy=None,dtime=86400,maxit=10000,error=0.000001,solver="bicgstab",relax=1,al=0.0,at=0.0,loops=1,stab="full",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`c : str | np.ndarray, required`**
   - The initial concentration in [kg/m^3]
   - Used as: input, raster, name

2. **`phead : str | np.ndarray, required`**
   - The piezometric head in [m]
   - Used as: input, raster, name

3. **`hc_x : str | np.ndarray, required`**
   - The x-part of the hydraulic conductivity tensor in [m/s]
   - Used as: input, raster, name

4. **`hc_y : str | np.ndarray, required`**
   - The y-part of the hydraulic conductivity tensor in [m/s]
   - Used as: input, raster, name

5. **`status : str | np.ndarray, required`**
   - The status for each cell, = 0 - inactive cell, 1 - active cell, 2 - dirichlet- and 3 - transfer boundary condition
   - Used as: input, raster, name

6. **`diff_x : str | np.ndarray, required`**
   - The x-part of the diffusion tensor in [m^2/s]
   - Used as: input, raster, name

7. **`diff_y : str | np.ndarray, required`**
   - The y-part of the diffusion tensor in [m^2/s]
   - Used as: input, raster, name

8. **`q : str | np.ndarray, optional`**
   - Groundwater sources and sinks in [m^3/s]
   - Used as: input, raster, name

9. **`cin : str, optional`**
   - Concentration sources and sinks bounded to a water source or sink in [kg/s]
   - Used as: input, raster, name

10. **`cs : str, required`**
   - Concentration of inner sources and inner sinks in [kg/s] (i.e. a chemical reaction)
   - Used as: input, raster, name

11. **`rd : str | np.ndarray, required`**
   - Retardation factor [-]
   - Used as: input, raster, name

12. **`nf : str | np.ndarray, required`**
   - Effective porosity [-]
   - Used as: input, raster, name

13. **`top : str | np.ndarray, required`**
   - Top surface of the aquifer in [m]
   - Used as: input, raster, name

14. **`bottom : str | np.ndarray, required`**
   - Bottom surface of the aquifer in [m]
   - Used as: input, raster, name

15. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - The resulting concentration of the numerical solute transport calculation will be written to this map. [kg/m^3]
   - Used as: output, raster, name

16. **`vx : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Calculate and store the groundwater filter velocity vector part in x direction [m/s]\

17. **`vy : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Calculate and store the groundwater filter velocity vector part in y direction [m/s]\

18. **`dtime : float, required`**
   - The calculation time in seconds
   - Default: 86400

19. **`maxit : int, optional`**
   - Maximum number of iteration used to solve the linear equation system
   - Default: 10000

20. **`error : float, optional`**
   - Error break criteria for iterative solver
   - Default: 0.000001

21. **`solver : str, optional`**
   - The type of solver which should solve the linear equation system
   - Used as: name
   - Allowed values: gauss, lu, jacobi, sor, bicgstab

22. **`relax : float, optional`**
   - The relaxation parameter used by the jacobi and sor solver for speedup or stabilizing
   - Default: 1

23. **`al : float, optional`**
   - The longditudinal dispersivity length. [m]
   - Default: 0.0

24. **`at : float, optional`**
   - The transversal dispersivity length. [m]
   - Default: 0.0

25. **`loops : float, optional`**
   - Use this number of time loops if the CFL flag is off. The timestep will become dt/loops.
   - Default: 1

26. **`stab : str, optional`**
   - Set the flow stabilizing scheme (full or exponential upwinding).
   - Allowed values: full, exp
   - Default: full

27. **`flags : str, optional`**
   - Allowed values: f, c
   - f
   - Use a full filled quadratic linear equation system, default is a sparse linear equation system.
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.solute.transport.html#__tabbed_2_3) for all details)*

28. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

29. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

30. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

31. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 31 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.solute.transport.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

This numerical program calculates numerical implicit transient and
steady state solute transport in porous media in the saturated zone of
an aquifer. The computation is based on raster maps and the current
region settings. All initial- and boundary-conditions must be provided
as raster maps. The unit of the coordinate reference system must be
meters.

This module is sensitive to mask settings. All cells which are outside
the mask are ignored and handled as no flow boundaries. This module calculates the concentration of the solution and optional
the velocity field, based on the hydraulic conductivity, the effective
porosity and the initial piecometric heads. The vector components can be
visualized with paraview if they are exported with r.out.vtk.

Use r.gwflow to compute the piezometric heights of the
aquifer. The piezometric heights and the hydraulic conductivity are used
to compute the flow direction and the mean velocity of the groundwater.
This is the base of the solute transport computation.

The solute transport will always be calculated transient. For stady
state computation set the timestep to a large number (billions of
seconds).

To reduce the numerical dispersion, which is a consequence of the
convection term and the finite volume discretization, you can use small
time steps and choose between full and exponential upwinding.

---

## See Also

Related tools:
- [`r.gwflow`](https://grass.osgeo.org/grass-devel/manuals/r.gwflow.html)
- [`r3.gwflow`](https://grass.osgeo.org/grass-devel/manuals/r3.gwflow.html)
- [`r.out.vtk`](https://grass.osgeo.org/grass-devel/manuals/r.out.vtk.html)

---

## Resources

- [Official r.solute.transport manual](https://grass.osgeo.org/grass-devel/manuals/r.solute.transport.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.solute.transport.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
