# r.contour

**Category**: raster

## Description

Produces a vector map of specified contours from a raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_contour(input,output,step=None,levels=None,minlevel=None,maxlevel=None,cut=2,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`step : float, optional`**
   - Increment between contour levels

4. **`levels : float | list[float] | str, optional`**
   - List of contour levels

5. **`minlevel : float, optional`**
   - Minimum contour level

6. **`maxlevel : float, optional`**
   - Maximum contour level

7. **`cut : int, optional`**
   - Minimum number of points for a contour line (0 -> no limit)
   - Default: 2

8. **`flags : str, optional`**
   - Allowed values: t
   - t
   - Do not create attribute table

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.contour.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.contour produces a vector map of specified contours from input
raster map. Contours can be produced using a comma-separated list of
values in levels , or at some regular increment using the step parameter, using minlevel and maxlevel as minimum and maximum
contour values, respectively. If no minlevel or maxlevel is
specified, the minimum and maximum cell values in the input raster
map will be used.

---

## Authors

Terry Baker, U.S. Army Construction Engineering Research Laboratory 3/2001: cut parameter and fixes by Andrea Aime ( aaime@libero.it )

---

## Resources

- [Official r.contour manual](https://grass.osgeo.org/grass-devel/manuals/r.contour.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.contour.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
