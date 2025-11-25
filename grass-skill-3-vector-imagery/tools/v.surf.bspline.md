# v.surf.bspline

**Category**: vector

## Description

Performs bicubic or bilinear spline interpolation with Tykhonov regularization.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_surf_bspline(input,layer="1",column=None,sparse_input=None,output=None,raster_output=None,mask=None,ew_step=None,ns_step=None,method="bilinear",lambda_i=0.01,solver="cholesky",maxit=10000,error=0.000001,memory=300,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector point map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`column : str, optional`**
   - Name of the attribute column with values to be used for approximation
   - If not given and input is 3D vector map then z-coordinates are used.
   - Used as: input, dbcolumn, name

4. **`sparse_input : str, optional`**
   - Name of input vector map with sparse points
   - Or data source for direct OGR access
   - Used as: input, vector, name

5. **`output : str, optional`**
   - Name for output vector map
   - Used as: output, vector, name

6. **`raster_output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map
   - Used as: output, raster, name

7. **`mask : str | np.ndarray, optional`**
   - Raster map to use for masking (applies to raster output only)
   - Only cells that are not NULL and not zero are interpolated
   - Used as: input, raster, name

8. **`ew_step : float, optional`**
   - Length of each spline step in the east-west direction
   - Default: 4 * east-west resolution

9. **`ns_step : float, optional`**
   - Length of each spline step in the north-south direction
   - Default: 4 * north-south resolution

10. **`method : str, optional`**
   - Spline interpolation algorithm
   - Allowed values: bilinear, bicubic
   - bilinear: Bilinear interpolation
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.surf.bspline.html#__tabbed_2_3) for all details)*

11. **`lambda_i : float, optional`**
   - Tykhonov regularization parameter (affects smoothing)
   - Default: 0.01

12. **`solver : str, optional`**
   - The type of solver which should solve the symmetric linear equation system
   - Used as: name
   - Allowed values: cholesky, cg

13. **`maxit : int, optional`**
   - Maximum number of iteration used to solve the linear equation system
   - Default: 10000

14. **`error : float, optional`**
   - Error break criteria for iterative solver
   - Default: 0.000001

15. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

16. **`flags : str, optional`**
   - Allowed values: c, e
   - c
   - Find the best Tykhonov regularizing parameter using a "leave-one-out" cross validation method
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.surf.bspline.html#__tabbed_2_3) for all details)*

17. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

18. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

19. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

20. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 20 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.surf.bspline.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.surf.bspline performs a bilinear/bicubic spline interpolation with
Tykhonov regularization. The input is a 2D or 3D vector point layer. Values to interpolate can be the z values of 3D points or the
values in a user-specified attribute column in a 2D or 3D vector layer.
Output can be a raster ( raster_output ) or vector ( output ) layer.
Optionally, a "sparse point" vector layer can be input which indicates
the location of output vector points.

---

## See Also

Related tools:
- [`v.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/v.surf.idw.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)

---

## Authors

Original version (s.bspline.reg) in GRASS 5.4: Maria Antonia Brovelli,
Massimiliano Cannata, Ulisse Longoni, Mirko Reguzzoni Update for GRASS 6 and improvements: Roberto Antolin

---

## Resources

- [Official v.surf.bspline manual](https://grass.osgeo.org/grass-devel/manuals/v.surf.bspline.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.surf.bspline.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
