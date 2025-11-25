# r.stats

**Category**: raster

## Description

Generates area statistics for raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_stats(input,output=None,separator=None,null_value="*",nsteps=255,sort=None,format="plain",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - Name of raster map(s) to report on
   - Used as: input, raster, name

2. **`output : str, optional`**
   - Name for output file (if omitted or "-" output to stdout)
   - Used as: output, file, name

3. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

4. **`null_value : str, optional`**
   - String representing NULL value
   - Used as: string
   - Default: *

5. **`nsteps : int, optional`**
   - Number of floating-point subranges to collect stats from
   - Default: 255

6. **`sort : str, optional`**
   - Sort output statistics by cell counts
   - Default: sorted by categories or intervals
   - Allowed values: asc, desc
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.stats.html#__tabbed_2_3) for all details)*

7. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, csv, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.stats.html#__tabbed_2_3) for all details)*

8. **`flags : str, optional`**
   - Allowed values: a, c, p, l, 1, g, x, A, r, n, N, C, i
   - a
   - Print area totals in square meters
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.stats.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.stats.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.stats calculates the area present in each of the categories or
floating-point intervals of user-selected input raster map. Area
statistics are given in units of square meters and/or cell counts. This
analysis uses the current geographic region ( g.region )
and mask settings ( r.mask ). The output statistics can be
saved to a output file.

Area statistics is printed in square meters for each category when -a is given. Similarly if -c flag is chosen, areas will be
stated also in number of cells.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.report`](https://grass.osgeo.org/grass-devel/manuals/r.report.html)
- [`r.coin`](https://grass.osgeo.org/grass-devel/manuals/r.coin.html)
- [`r.describe`](https://grass.osgeo.org/grass-devel/manuals/r.describe.html)
- [`r.stats.quantile`](https://grass.osgeo.org/grass-devel/manuals/r.stats.quantile.html)
- [`r.stats.zonal`](https://grass.osgeo.org/grass-devel/manuals/r.stats.zonal.html)
- [`r.statistics`](https://grass.osgeo.org/grass-devel/manuals/r.statistics.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)

---

## Authors

Michael Shapiro, U.S. Army Construction Engineering Research
Laboratory Sort option by Martin Landa, Czech Technical University in Prague, 2013

---

## Resources

- [Official r.stats manual](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.stats.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
