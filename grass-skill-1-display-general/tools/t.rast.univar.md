# t.rast.univar

**Category**: temporal

## Description

Calculates univariate statistics from the non-null cells for each registered raster map of a space time raster dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_univar(input,zones=None,nprocs=0,output=None,percentile=None,where=None,region_relation=None,separator="pipe",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`zones : str | np.ndarray, optional`**
   - Raster map used for zoning, must be of type CELL
   - Used as: input, raster, name

3. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

4. **`output : str, optional`**
   - Name for output file
   - Used as: output, file, name

5. **`percentile : float | list[float] | str, optional`**
   - Percentile to calculate (requires extended statistics flag)
   - Allowed values: 0-100

6. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

7. **`region_relation : str, optional`**
   - Process only maps with this spatial relation to the current computational region
   - Allowed values: overlaps, contains, is_contained

8. **`separator : str, optional`**
   - Field separator character between the output columns
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

9. **`flags : str, optional`**
   - Allowed values: e, r, u
   - e
   - Calculate extended statistics
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.univar.html#__tabbed_2_3) for all details)*

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.univar.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast.univar calculates univariate statistics from the non-null cells
for each registered raster map of a space time raster dataset.

By default it returns the name of the map, the semantic label of the
map, the start and end date of the map and the following values: mean,
minimum and maximum vale, mean_of_abs, standard deviation, variance,
coeff_var, number of null cells, total number of cells.

Using the e flag it can calculate also extended statistics: first
quartile, median value, third quartile and percentile 90.

If a zones raster map is provided, statistics are computed for each
zone (category) in that input raster map. The zones option does not
support space time raster datasets (STRDS) but only a single, static
raster map.

Space time raster datasets may contain raster maps with varying spatial
extent like for example series of scenes of satellite images. With the region_relation option, computations can be limited to maps of the
space time raster dataset that have a given spatial relation to the
current computational region. Supported spatial relations are:

---

## See Also

Related tools:
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)

---

## Resources

- [Official t.rast.univar manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.univar.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.univar.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
