# t.rast.series

**Category**: temporal

## Description

Performs different aggregation algorithms from r.series on all or a subset of raster maps in a space time raster dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_series(input,method="average",quantile=None,order="start_time",nprocs=0,memory=300,where=None,output,file_limit=1000,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`method : str | list[str], required`**
   - Aggregate operation to be performed on the raster maps
   - Allowed values: average, count, median, mode, minimum, min_raster, maximum, max_raster, stddev, range, sum, variance, diversity, slope, offset, detcoeff, quart1, quart3, perc90, quantile, skewness, kurtosis
   - Default: average

3. **`quantile : float | list[float] | str, optional`**
   - Quantile to calculate for method=quantile
   - Allowed values: 0.0-1.0

4. **`order : str | list[str], optional`**
   - Sort the maps by category
   - Allowed values: id,  name,  creator,  mapset,  creation_time,  modification_time,  start_time,  end_time,  north,  south,  west,  east,  min,  max
   - Default: start_time

5. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

6. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

7. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

8. **`output : str | list[str], required`**
   - Name for output raster map(s)
   - Used as: output, raster, name

9. **`file_limit : int, optional`**
   - The maximum number of open files allowed for each r.series process
   - Default: 1000

10. **`flags : str, optional`**
   - Allowed values: t, n
   - t
   - Do not assign the space time raster dataset start and end time to the output map
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.series.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.series.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The input of this module is a single space time raster dataset, the
output is a single raster map layer. A subset of the input space time
raster dataset can be selected using the where option. The sorting
of the raster map layer can be set using the order option. Be aware
that the order of the maps can significantly influence the result of the
aggregation (e.g.: slope). By default the maps are ordered by start_time .

t.rast.series is a simple wrapper for the raster module r.series .
It supports a subset of the aggregation methods of r.series .

---

## See Also

Related tools:
- [`r.series`](https://grass.osgeo.org/grass-devel/manuals/r.series.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.rast.series manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.series.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.series.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
