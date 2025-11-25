# r.univar

**Category**: raster

## Description

Calculates univariate statistics from the non-null cells of a raster map. Statistics include number of cells counted, minimum and maximum cell values, range, arithmetic mean, population variance, standard deviation, coefficient of variation, and sum.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_univar(map,zones=None,output=None,percentile=90,nprocs=0,separator=None,format="plain",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | list[str], required`**
   - Name of raster map(s)
   - Used as: input, raster, name

2. **`zones : str | np.ndarray, optional`**
   - Raster map used for zoning, must be of type CELL
   - Used as: input, raster, name

3. **`output : str, optional`**
   - Name for output file (if omitted or "-" output to stdout)
   - Used as: output, file, name

4. **`percentile : float | list[float] | str, optional`**
   - Percentile to calculate (requires extended statistics flag)
   - Allowed values: 0-100
   - Default: 90

5. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

6. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

7. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, shell, csv, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.univar.html#__tabbed_2_3) for all details)*

8. **`flags : str, optional`**
   - Allowed values: g, e, t, r
   - g
   - Print the stats in shell script style [deprecated]
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.univar.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.univar.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.univar calculates the univariate statistics of one or several raster
map(s). This includes the number of cells counted, minimum and maximum
cell values, range, arithmetic mean, population variance, standard
deviation, coefficient of variation, and sum. Statistics are calculated
separately for every category/zone found in the zones input map if
given. If the -e extended statistics flag is given the 1st quartile,
median, 3rd quartile, and given percentile are calculated. If the format=shell is given the results are presented in a format suitable for
use in a shell script. If the format=csv is given the results are
presented in tabular format with the given field separator. The table
can immediately be converted to a vector attribute table which can then
be linked to a vector, e.g. the vector that was rasterized to create the zones input raster.

When multiple input maps are given to r.univar , the overall statistics
are calculated. This is useful for a time series of the same variable,
as well as for the case of a segmented/tiled dataset. Allowing multiple
raster maps to be specified saves the user from using a temporary raster
map for the result of r.series or r.patch .

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r3.univar`](https://grass.osgeo.org/grass-devel/manuals/r3.univar.html)
- [`r.mode`](https://grass.osgeo.org/grass-devel/manuals/r.mode.html)
- [`r.quantile`](https://grass.osgeo.org/grass-devel/manuals/r.quantile.html)
- [`r.series`](https://grass.osgeo.org/grass-devel/manuals/r.series.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)
- [`r.stats.quantile`](https://grass.osgeo.org/grass-devel/manuals/r.stats.quantile.html)
- [`r.stats.zonal`](https://grass.osgeo.org/grass-devel/manuals/r.stats.zonal.html)
- [`r.statistics`](https://grass.osgeo.org/grass-devel/manuals/r.statistics.html)
- [`v.rast.stats`](https://grass.osgeo.org/grass-devel/manuals/v.rast.stats.html)
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)

---

## Authors

Hamish Bowman, Otago University, New Zealand Extended statistics by Martin Landa Multiple input map support by Ivan Shmakov Zonal loop by Markus Metz

---

## Resources

- [Official r.univar manual](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.univar.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
