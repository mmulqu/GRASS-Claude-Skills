# r.quantile

**Category**: raster

## Description

Compute quantiles using two passes.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_quantile(input,quantiles=4,percentiles=None,bins=1000000,file=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`quantiles : int, optional`**
   - Number of quantiles
   - Default: 4

3. **`percentiles : float | list[float] | str, optional`**
   - List of percentiles

4. **`bins : int, optional`**
   - Number of bins to use
   - Default: 1000000

5. **`file : str, optional`**
   - Name for output file (if omitted or "-" output to stdout)
   - Used as: output, file, name

6. **`flags : str, optional`**
   - Allowed values: r
   - r
   - Generate recode rules based on quantile-defined intervals

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.quantile computes quantiles in a manner suitable for use with large
amounts of data. It is using two passes.

---

## See Also

Related tools:
- [`r.mode`](https://grass.osgeo.org/grass-devel/manuals/r.mode.html)
- [`r.quant`](https://grass.osgeo.org/grass-devel/manuals/r.quant.html)
- [`r.recode`](https://grass.osgeo.org/grass-devel/manuals/r.recode.html)
- [`r.series`](https://grass.osgeo.org/grass-devel/manuals/r.series.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)
- [`r.stats.quantile`](https://grass.osgeo.org/grass-devel/manuals/r.stats.quantile.html)
- [`r.stats.zonal`](https://grass.osgeo.org/grass-devel/manuals/r.stats.zonal.html)
- [`r.statistics`](https://grass.osgeo.org/grass-devel/manuals/r.statistics.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)
- [`v.rast.stats`](https://grass.osgeo.org/grass-devel/manuals/v.rast.stats.html)

---

## Authors

Glynn Clements Markus Metz

---

## Resources

- [Official r.quantile manual](https://grass.osgeo.org/grass-devel/manuals/r.quantile.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.quantile.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
