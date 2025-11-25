# r.series

**Category**: raster

## Description

Makes each output cell value a function of the values assigned to the corresponding cells in the input raster map layers.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_series(input=None,file=None,output,method,quantile=None,weights=None,range=None,nprocs=0,memory=300,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], optional`**
   - Name of input raster map(s)
   - Used as: input, raster, name

2. **`file : str | io.StringIO, optional`**
   - Input file with one raster map name and optional one weight per line, field separator between name and weight is | (pipe)
   - Used as: input, file, name

3. **`output : str | list[str], required`**
   - Name for output raster map
   - Used as: output, raster, name

4. **`method : str | list[str], required`**
   - Aggregate operation
   - Allowed values: average, count, median, mode, minimum, min_raster, maximum, max_raster, stddev, range, sum, variance, diversity, slope, offset, detcoeff, tvalue, quart1, quart3, perc90, quantile, skewness, kurtosis

5. **`quantile : float | list[float] | str, optional`**
   - Quantile to calculate for method=quantile
   - Allowed values: 0.0-1.0

6. **`weights : float | list[float] | str, optional`**
   - Weighting factor for each input map, default value is 1.0 for each input map

7. **`range : tuple[float, float] | list[float] | str, optional`**
   - Ignore values outside this range
   - Used as: lo,hi

8. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

9. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

10. **`flags : str, optional`**
   - Allowed values: n, z
   - n
   - Propagate NULLs
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.series.html#__tabbed_2_3) for all details)*

11. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

12. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

13. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

14. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.series.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.series makes each output cell value a function of the values
assigned to the corresponding cells in the input raster map layers.

Figure: Illustration for an average of three input rasters

Following methods are available:

Note that most parameters accept multiple answers, allowing multiple
aggregates to be computed in a single run, e.g.:

or:

The same number of values must be provided for all options.

---

## See Also

Related tools:
- [`g.list`](https://grass.osgeo.org/grass-devel/manuals/g.list.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.quantile`](https://grass.osgeo.org/grass-devel/manuals/r.quantile.html)
- [`r.series.accumulate`](https://grass.osgeo.org/grass-devel/manuals/r.series.accumulate.html)
- [`r.series.interp`](https://grass.osgeo.org/grass-devel/manuals/r.series.interp.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)

---

## Resources

- [Official r.series manual](https://grass.osgeo.org/grass-devel/manuals/r.series.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.series.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
