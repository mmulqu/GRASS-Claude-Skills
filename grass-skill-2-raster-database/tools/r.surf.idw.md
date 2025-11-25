# r.surf.idw

**Category**: raster

## Description

Provides surface interpolation from raster point data by Inverse Distance Squared Weighting.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_surf_idw(input,output,npoints=12,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`npoints : int, optional`**
   - Number of interpolation points
   - Default: 12

4. **`flags : str, optional`**
   - Allowed values: e
   - e
   - Output is the interpolation error

5. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.surf.idw fills a grid cell (raster) matrix with interpolated values
generated from input raster data points. It uses a numerical
approximation technique based on distance squared weighting of the
values of nearest data points. The number of nearest data points used to
determined the interpolated value of a cell can be specified by the user
(default: 12 nearest data points).

If there is a current working mask, it applies to the output raster map.
Only those cells falling within the mask will be assigned interpolated
values. The search procedure for the selection of nearest neighboring
points will consider all input data, without regard to the mask. The -e flag is the error analysis option that interpolates values only
for those cells of the input raster map which have non-zero values and
outputs the difference (see NOTES below).

The npoints parameter defines the number of nearest data points used
to determine the interpolated value of an output raster cell.

---

## See Also

Related tools:
- [`r.surf.contour`](https://grass.osgeo.org/grass-devel/manuals/r.surf.contour.html)
- [`r.surf.gauss`](https://grass.osgeo.org/grass-devel/manuals/r.surf.gauss.html)
- [`r.surf.fractal`](https://grass.osgeo.org/grass-devel/manuals/r.surf.fractal.html)
- [`r.surf.random`](https://grass.osgeo.org/grass-devel/manuals/r.surf.random.html)
- [`v.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/v.surf.idw.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)

---

## Resources

- [Official r.surf.idw manual](https://grass.osgeo.org/grass-devel/manuals/r.surf.idw.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.surf.idw.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
