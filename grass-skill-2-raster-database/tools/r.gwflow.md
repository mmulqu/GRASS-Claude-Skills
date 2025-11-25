# r.gwflow

**Category**: raster

## Description

Numerical calculation program for transient, confined and unconfined groundwater flow in two dimensions.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_gwflow(phead,status,hc_x,hc_y,q=None,s,recharge=None,top,bottom,output,vx=None,vy=None,budget=None,type="confined",river_bed=None,river_head=None,river_leak=None,drain_bed=None,drain_leak=None,dtime=86400,maxit=10000,maxit=25,error=0.000001,solver="cg",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`phead : str | np.ndarray, required`**
   - Name of input raster map with initial piezometric head in [m]
   - Used as: input, raster, name

2. **`status : str | np.ndarray, required`**
   - Name of input raster map providing boundary condition status: 0-inactive, 1-active, 2-dirichlet
   - Used as: input, raster, name

3. **`hc_x : str | np.ndarray, required`**
   - Name of input raster map with x-part of the hydraulic conductivity tensor in [m/s]
   - Used as: input, raster, name

4. **`hc_y : str | np.ndarray, required`**
   - Name of input raster map with y-part of the hydraulic conductivity tensor in [m/s]
   - Used as: input, raster, name

5. **`q : str | np.ndarray, optional`**
   - Name of input raster map with water sources and sinks in [m^3/s]
   - Used as: input, raster, name

6. **`s : str | np.ndarray, required`**
   - Name of input raster map with storativity for confined or effective porosity for unconfined groundwater flow booth in [-]
   - Used as: input, raster, name

7. **`recharge : str | np.ndarray, optional`**
   - Recharge input raster map e.g: 6*10^-9 per cell in [m^3/s*m^2]
   - Used as: input, raster, name

8. **`top : str | np.ndarray, required`**
   - Name of input raster map describing the top surface of the aquifer in [m]
   - Used as: input, raster, name

9. **`bottom : str | np.ndarray, required`**
   - Name of input raster map describing the bottom surface of the aquifer in [m]
   - Used as: input, raster, name

10. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Output raster map storing the numerical result [m]
   - Used as: output, raster, name

11. **`vx : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Output raster map to store the groundwater filter velocity vector part in x direction [m/s]
   - Used as: output, raster, name

12. **`vy : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Output raster map to store the groundwater filter velocity vector part in y direction [m/s]
   - Used as: output, raster, name

13. **`budget : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Output raster map to store the groundwater budget for each cell [m^3/s]
   - Used as: output, raster, name

14. **`type : str, required`**
   - The type of groundwater flow
   - Allowed values: confined, unconfined
   - Default: confined

15. **`river_bed : str | np.ndarray, optional`**
   - Name of input raster map providing the height of the river bed in [m]
   - Used as: input, raster, name

16. **`river_head : str | np.ndarray, optional`**
   - Name of input raster map providing the water level (head) of the river with leakage connection in [m]
   - Used as: input, raster, name

17. **`river_leak : str | np.ndarray, optional`**
   - Name of input raster map providing the leakage coefficient of the river bed in [1/s].
   - Used as: input, raster, name

18. **`drain_bed : str, optional`**
   - Name of input raster map providing the height of the drainage bed in [m]
   - Used as: input, raster, name

19. **`drain_leak : str | np.ndarray, optional`**
   - Name of input raster map providing the leakage coefficient of the drainage bed in [1/s]
   - Used as: input, raster, name

20. **`dtime : float, required`**
   - The calculation time in seconds
   - Default: 86400

21. **`maxit : int, optional`**
   - Maximum number of iteration used to solve the linear equation system
   - Default: 10000

22. **`maxit : int, optional`**
   - The maximum number of iterations in the linearization approach
   - Default: 25

23. **`error : float, optional`**
   - Error break criteria for iterative solver
   - Default: 0.000001

24. **`solver : str, optional`**
   - The type of solver which should solve the symmetric linear equation system
   - Used as: name
   - Allowed values: cg, pcg, cholesky

25. **`flags : str, optional`**
   - Allowed values: f
   - f
   - Allocate a full quadratic linear equation system, default is a sparse linear equation system.

26. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

27. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

28. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

29. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 29 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.gwflow.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.gwflow is a numerical program which calculates implicit transient,
confined and unconfined groundwater flow in two dimensions based on
raster maps and the current region settings. All initial and boundary
conditions must be provided as raster maps. The unit of the current
project's coordinate reference system must be meters.

This module is sensitive to mask settings. All cells which are outside
the mask are ignored and handled as no flow boundaries.

Workflow of r.gwflow

r.gwflow calculates the piezometric head and optionally the water
budget and the filter velocity field, based on the hydraulic
conductivity and the piezometric head. The vector components can be
visualized with paraview if they are exported with r.out.vtk .

The groundwater flow will always be calculated transient. For stady
state computation set the timestep to a large number (billions of
seconds) or set the storativity/ effective porosity raster map to
zero.

The water budget is calculated for each non inactive cell. The sum of
the budget for each non inactive cell must be near zero. This is an
indicator of the quality of the numerical result.

---

## See Also

Related tools:
- [`r.solute.transport`](https://grass.osgeo.org/grass-devel/manuals/r.solute.transport.html)
- [`r3.gwflow`](https://grass.osgeo.org/grass-devel/manuals/r3.gwflow.html)
- [`r.out.vtk`](https://grass.osgeo.org/grass-devel/manuals/r.out.vtk.html)

---

## Resources

- [Official r.gwflow manual](https://grass.osgeo.org/grass-devel/manuals/r.gwflow.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.gwflow.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
