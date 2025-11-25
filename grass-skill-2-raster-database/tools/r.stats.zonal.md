# r.stats.zonal

**Category**: raster

## Description

Calculates category or object oriented statistics (accumulator-based statistics).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_stats_zonal(base,cover,method,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`base : str | np.ndarray, required`**
   - Name of base raster map
   - Used as: input, raster, name

2. **`cover : str | np.ndarray, required`**
   - Name of cover raster map
   - Used as: input, raster, name

3. **`method : str, required`**
   - Method of object-based statistic
   - Allowed values: count, sum, min, max, range, average, avedev, variance, stddev, skewness, kurtosis, variance2, stddev2, skewness2, kurtosis2
   - count: Count of values in specified objects
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.stats.zonal.html#__tabbed_2_3) for all details)*

4. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Resultant raster map
   - Used as: output, raster, name

5. **`flags : str, optional`**
   - Allowed values: c, r
   - c
   - Cover values extracted from the category labels of the cover map
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.stats.zonal.html#__tabbed_2_3) for all details)*

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

r.stats.zonal is a tool to analyse exploratory statistics of a
floating-point "cover layer" according to how it intersects with objects
in a "base layer". A variety of standard statistical measures are
possible. This type of analysis is often called zonal statistics . The
zones are specified as the base raster map and the statistics are
computed from cells in the cover raster map. Notably, the output of
this module is spatial: The resulting values are recorded as cell values
in the output raster map.

---

## Resources

- [Official r.stats.zonal manual](https://grass.osgeo.org/grass-devel/manuals/r.stats.zonal.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.stats.zonal.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
