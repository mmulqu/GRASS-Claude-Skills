# r.param.scale

**Category**: raster

## Description

Extracts terrain parameters from a DEM. Uses a multi-scale approach by taking fitting quadratic parameters to any size window (via least squares).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_param_scale(input,output,slope_tolerance=1.0,curvature_tolerance=0.0001,size=3,method="elev",exponent=0.0,zscale=1.0,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map containing morphometric parameter
   - Used as: output, raster, name

3. **`slope_tolerance : float, optional`**
   - Slope tolerance that defines a 'flat' surface (degrees)
   - Default: 1.0

4. **`curvature_tolerance : float, optional`**
   - Curvature tolerance that defines 'planar' surface
   - Default: 0.0001

5. **`size : int, optional`**
   - Size of processing window (odd number only)
   - Allowed values: 3-499
   - Default: 3

6. **`method : str, optional`**
   - Morphometric parameter in 'size' window to calculate
   - Allowed values: elev, slope, aspect, profc, planc, longc, crosc, minic, maxic, feature
   - Default: elev

7. **`exponent : float, optional`**
   - Exponent for distance weighting (0.0-4.0)
   - Default: 0.0

8. **`zscale : float, optional`**
   - Vertical scaling factor
   - Default: 1.0

9. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Constrain model through central window cell

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.param.scale.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.param.scale extracts terrain parameters from a digital elevation
model. Uses a multi-scale approach by fitting a bivariate quadratic
polynomial to a given window size using least squares.

The module calculates the following parameters (terminology is from
Wood, 1996 with related terminology used in other GRASS modules listed
in brackets):

---

## See Also

Related tools:
- [`r.geomorphon`](https://grass.osgeo.org/grass-devel/manuals/r.geomorphon.html)
- [`r.slope.aspect`](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)

---

## Authors

Jo Wood - ASSIST's
home
Update to FP 3/2002: L. Potrich, M. Neteler, S. Menegon (ITC-irst)

---

## Resources

- [Official r.param.scale manual](https://grass.osgeo.org/grass-devel/manuals/r.param.scale.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.param.scale.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
