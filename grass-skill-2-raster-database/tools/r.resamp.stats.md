# r.resamp.stats

**Category**: raster

## Description

Resamples raster map layers to a coarser grid using aggregation.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_resamp_stats(input,output,method="average",quantile=0.5,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`method : str, optional`**
   - Aggregation method
   - Allowed values: average, median, mode, minimum, maximum, range, quart1, quart3, perc90, sum, variance, stddev, quantile, count, diversity
   - Default: average

4. **`quantile : float, optional`**
   - Quantile to calculate for method=quantile
   - Allowed values: 0.0-1.0
   - Default: 0.5

5. **`flags : str, optional`**
   - Allowed values: n, w
   - n
   - Propagate NULLs
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.resamp.stats.html#__tabbed_2_3) for all details)*

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

r.resamp.stats fills a grid cell (raster) matrix with aggregated
values generated from a set of input layer data points.

Without the -w switch, the aggregate is computed over all of the input
cells whose centers lie within the output cell.

With the -w switch, the aggregate uses the values from all input cells
which intersect the output cell, weighted according to the proportion of
the source cell which lies inside the output cell. This is slower, but
produces a more accurate result.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.resample`](https://grass.osgeo.org/grass-devel/manuals/r.resample.html)
- [`r.resamp.rst`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.rst.html)
- [`r.resamp.filter`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.filter.html)
- [`r.resamp.interp`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.interp.html)
- [`r.neighbors`](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)

---

## Resources

- [Official r.resamp.stats manual](https://grass.osgeo.org/grass-devel/manuals/r.resamp.stats.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.resamp.stats.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
