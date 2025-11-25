# t.rast.aggregate

**Category**: temporal

## Description

Aggregates temporally the maps of a space time raster dataset by a user defined granularity.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_aggregate(input,output,basename,suffix="gran",granularity,method="average",offset=0,nprocs=1,file_limit=1000,sampling="contains",where=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`output : str, required`**
   - Name of the output space time raster dataset
   - Used as: output, strds, name

3. **`basename : str, required`**
   - Basename of the new generated output maps
   - Either a numerical suffix or the start time (s-flag) separated by an underscore will be attached to create a unique identifier

4. **`suffix : str, optional`**
   - Suffix to add at basename: set 'gran' for granularity, 'time' for the full time format, 'num' for numerical suffix with a specific number of digits (default %05)
   - Default: gran

5. **`granularity : str, required`**
   - Aggregation granularity, format absolute time "x years, x months, x weeks, x days, x hours, x minutes, x seconds" or an integer value for relative time

6. **`method : str, required`**
   - Aggregate operation to be performed on the raster maps
   - Allowed values: average, count, median, mode, minimum, min_raster, maximum, max_raster, stddev, range, sum, variance, diversity, slope, offset, detcoeff, quart1, quart3, perc90, quantile, skewness, kurtosis
   - Default: average

7. **`offset : int, optional`**
   - Offset that is used to create the output map ids, output map id is generated as: basename_ (count + offset)
   - Default: 0

8. **`nprocs : int, optional`**
   - Number of r.series processes to run in parallel
   - Default: 1

9. **`file_limit : int, optional`**
   - The maximum number of open files allowed for each r.series process
   - Default: 1000

10. **`sampling : str | list[str], optional`**
   - The method to be used for sampling the input dataset
   - Used as: name
   - Allowed values: equal, overlaps, overlapped, starts, started, finishes, finished, during, contains

11. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

12. **`flags : str, optional`**
   - Allowed values: n
   - n
   - Register Null maps

13. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

14. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

15. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

16. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.aggregate.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast.aggregate temporally aggregates space time raster datasets by a
specific temporal granularity. This module support absolute and relative time . The temporal granularity of absolute time can be seconds, minutes, hours, days, weeks, months or years . Mixing of
granularities eg. "1 year, 3 months 5 days" is not supported. In case of
relative time the temporal unit of the input space time raster dataset
is used. The granularity must be specified with an integer value.

This module is sensitive to the current region and mask settings, hence
spatial extent and spatial resolution. In case the registered raster
maps of the input space time raster dataset have different spatial
resolutions, the default nearest neighbor resampling method is used for
runtime spatial aggregation.

---

## See Also

Related tools:
- [`t.rast.aggregate.ds`](https://grass.osgeo.org/grass-devel/manuals/t.rast.aggregate.ds.html)
- [`t.rast.extract`](https://grass.osgeo.org/grass-devel/manuals/t.rast.extract.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`r.series`](https://grass.osgeo.org/grass-devel/manuals/r.series.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.mask`](https://grass.osgeo.org/grass-devel/manuals/r.mask.html)

---

## Resources

- [Official t.rast.aggregate manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.aggregate.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.aggregate.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
