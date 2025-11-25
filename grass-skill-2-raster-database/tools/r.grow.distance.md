# r.grow.distance

**Category**: raster

## Description

Generates a raster map containing distances to nearest raster features and/or the value of the nearest non-null cell.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_grow_distance(input,distance=None,value=None,metric="euclidean",minimum_distance=None,maximum_distance=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`distance : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for distance output raster map
   - Used as: output, raster, name

3. **`value : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for value output raster map
   - Used as: output, raster, name

4. **`metric : str, optional`**
   - Metric
   - Allowed values: euclidean, squared, maximum, manhattan, geodesic
   - Default: euclidean

5. **`minimum_distance : float, optional`**
   - Minimum distance threshold

6. **`maximum_distance : float, optional`**
   - Maximum distance threshold

7. **`flags : str, optional`**
   - Allowed values: m, n
   - m
   - Output distances in meters instead of map units
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.grow.distance.html#__tabbed_2_3) for all details)*

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.grow.distance.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.grow.distance generates raster maps representing the distance to the
nearest non-null cell in the input map and/or the value of the nearest
non-null cell.

---

## See Also

Related tools:
- [`r.grow`](https://grass.osgeo.org/grass-devel/manuals/r.grow.html)
- [`r.distance`](https://grass.osgeo.org/grass-devel/manuals/r.distance.html)
- [`r.buffer`](https://grass.osgeo.org/grass-devel/manuals/r.buffer.html)
- [`r.cost`](https://grass.osgeo.org/grass-devel/manuals/r.cost.html)
- [`r.patch`](https://grass.osgeo.org/grass-devel/manuals/r.patch.html)

---

## Resources

- [Official r.grow.distance manual](https://grass.osgeo.org/grass-devel/manuals/r.grow.distance.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.grow.distance.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
