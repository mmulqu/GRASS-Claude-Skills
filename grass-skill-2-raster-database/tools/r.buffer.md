# r.buffer

**Category**: raster

## Description

Creates a raster map showing buffer zones surrounding cells that contain non-NULL category values.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_buffer(input,output,distances,units="meters",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`distances : float | list[float] | str, required`**
   - Distance zone(s)

4. **`units : str, optional`**
   - Units of distance
   - Allowed values: meters, kilometers, feet, miles, nautmiles
   - Default: meters

5. **`flags : str, optional`**
   - Allowed values: z
   - z
   - Ignore zero (0) data cells instead of NULL cells

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

r.buffer creates a new raster map showing buffer (a.k.a. "distance" or
"proximity") zones around all cells that contain non-NULL category
values in an existing raster map. The distances of buffer zones from
cells with non-zero category values are user-chosen and must be positive
value(s). Suppose, for example, that you want to place buffer zones
around roads. This program could create the raster map shown below on
the right based on road information contained in the raster map shown on
the left.

---

## See Also

Related tools:
- [`r.buffer.lowmem`](https://grass.osgeo.org/grass-devel/manuals/r.buffer.lowmem.html)
- [`r.grow`](https://grass.osgeo.org/grass-devel/manuals/r.grow.html)
- [`v.buffer`](https://grass.osgeo.org/grass-devel/manuals/v.buffer.html)

---

## Authors

Michael Shapiro, U.S. Army Construction Engineering Research
Laboratory James Westervelt, U.S. Army Construction Engineering Research Laboratory

---

## Resources

- [Official r.buffer manual](https://grass.osgeo.org/grass-devel/manuals/r.buffer.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.buffer.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
