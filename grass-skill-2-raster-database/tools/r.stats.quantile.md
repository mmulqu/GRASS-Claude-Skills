# r.stats.quantile

**Category**: raster

## Description

Compute category quantiles using two passes.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_stats_quantile(base,cover,quantiles=None,percentiles=50,bins=1000,output=None,file=None,separator=None,format="plain",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`base : str | np.ndarray, required`**
   - Name of base raster map
   - Used as: input, raster, name

2. **`cover : str | np.ndarray, required`**
   - Name of cover raster map
   - Used as: input, raster, name

3. **`quantiles : int, optional`**
   - Number of quantiles

4. **`percentiles : float | list[float] | str, optional`**
   - List of percentiles
   - Default: 50

5. **`bins : int, optional`**
   - Number of bins to use
   - Default: 1000

6. **`output : str | list[str], optional`**
   - Resultant raster map(s)
   - Used as: output, raster, name

7. **`file : str, optional`**
   - Name for output file (if omitted or "-" output to stdout)
   - Used as: output, file, name

8. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

9. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, csv, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.stats.quantile.html#__tabbed_2_3) for all details)*

10. **`flags : str, optional`**
   - Allowed values: r, p, t
   - r
   - Create reclass map with statistics as category labels
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.stats.quantile.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.stats.quantile.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.stats.quantile is a tool to analyse exploratory statistics of a
floating-point "cover layer" according to how it intersects with objects
in a "base layer". It provides quantile calculations as selected "zonal
statistics".

---

## See Also

Related tools:
- [`r.quantile`](https://grass.osgeo.org/grass-devel/manuals/r.quantile.html)
- [`r.stats.zonal`](https://grass.osgeo.org/grass-devel/manuals/r.stats.zonal.html)
- [`r.statistics`](https://grass.osgeo.org/grass-devel/manuals/r.statistics.html)

---

## Authors

Glynn Clements Markus Metz

---

## Resources

- [Official r.stats.quantile manual](https://grass.osgeo.org/grass-devel/manuals/r.stats.quantile.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.stats.quantile.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
