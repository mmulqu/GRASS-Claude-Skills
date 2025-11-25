# t.rast.aggregate.ds

**Category**: temporal

## Description

Aggregates data of an existing space time raster dataset using the time intervals of a second space time dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_aggregate_ds(input,sample,type="strds",output,basename,suffix="gran",method="average",offset=0,nprocs=1,sampling="contains",where=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`sample : str, required`**
   - Time intervals from this space time dataset (raster, vector or raster3d) are used for aggregation computation
   - Used as: input, stds, name

3. **`type : str, optional`**
   - Type of the space time dataset from which aggregation will be copied
   - Used as: name
   - Allowed values: strds, stvds, str3ds

4. **`Default: strds`**

5. **`output : str, required`**
   - Name of the output space time raster dataset
   - Used as: output, strds, name

6. **`basename : str, required`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier

7. **`suffix : str, optional`**
   - Suffix to add at basename: set 'gran' for granularity, 'time' for the full time format, 'num' for numerical suffix with a specific number of digits (default %05)
   - Default: gran

8. **`method : str, required`**
   - Aggregate operation to be performed on the raster maps
   - Allowed values: average, count, median, mode, minimum, min_raster, maximum, max_raster, stddev, range, sum, variance, diversity, slope, offset, detcoeff, quart1, quart3, perc90, quantile, skewness, kurtosis
   - Default: average

9. **`offset : int, optional`**
   - Offset that is used to create the output map ids, output map id is generated as: basename_ (count + offset)
   - Default: 0

10. **`nprocs : int, optional`**
   - Number of r.mapcalc processes to run in parallel
   - Default: 1

11. **`sampling : str | list[str], optional`**
   - The method to be used for sampling the input dataset
   - Used as: name
   - Allowed values: equal, overlaps, overlapped, starts, started, finishes, finished, during, contains

12. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

13. **`flags : str, optional`**
   - Allowed values: n
   - n
   - Register Null maps

14. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

15. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

16. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

17. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 17 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.aggregate.ds.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast.aggregate.ds works like t.rast.aggregate but instead of defining a fixed granularity for temporal aggregation the
time intervals of all maps registered in a second space time dataset
(can be STRDS, STR3DS or STVDS) are used to aggregate the maps of the
input space time raster dataset.

---

## See Also

Related tools:
- [`t.rast.aggregate`](https://grass.osgeo.org/grass-devel/manuals/t.rast.aggregate.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.rast.aggregate.ds manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.aggregate.ds.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.aggregate.ds.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
