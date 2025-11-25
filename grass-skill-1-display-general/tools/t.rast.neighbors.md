# t.rast.neighbors

**Category**: temporal

## Description

Performs a neighborhood analysis for each map in a space time raster dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_neighbors(input,output,where=None,region_relation=None,selection=None,size=3,method="average",weighting_function="none",weighting_factor=None,weight=None,quantile=None,basename,suffix="gran",semantic_labels="input",nprocs=1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`output : str, required`**
   - Name of the output space time raster dataset
   - Used as: output, strds, name

3. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

4. **`region_relation : str, optional`**
   - Process only maps with this spatial relation to the current computational region
   - Allowed values: overlaps,  contains,  is_contained

5. **`selection : str | np.ndarray, optional`**
   - Name of an input raster map to select the cells which should be processed
   - Used as: input, raster, name

6. **`size : int, optional`**
   - Neighborhood size
   - Default: 3

7. **`method : str, required`**
   - Aggregate operation to be performed on the raster maps
   - Allowed values: average, median, mode, minimum, maximum, range, stddev, sum, count, variance, diversity, interspersion, quart1, quart3, perc90, quantile
   - Default: average

8. **`weighting_function : str, optional`**
   - Weighting function
   - Allowed values: none, gaussian, exponential, file
   - none: No weighting
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.neighbors.html#__tabbed_2_3) for all details)*

9. **`weighting_factor : float, optional`**
   - Factor used in the selected weighting function (ignored for weighting_function=none and file)

10. **`weight : str | io.StringIO, optional`**
   - Text file containing weights
   - Used as: input, file, name

11. **`quantile : float | list[float] | str, optional`**
   - Quantile to calculate for method=quantile
   - Allowed values: 0.0-1.0

12. **`basename : str, required`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier

13. **`suffix : str, optional`**
   - Suffix to add at basename: set 'gran' for granularity, 'time' for the full time format, 'num' for numerical suffix with a specific number of digits (default %05)
   - Default: gran

14. **`semantic_labels : str, optional`**
   - Set semantic labels
   - Allowed values: input, method
   - input: copy semantic labels from input to output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.neighbors.html#__tabbed_2_3) for all details)*

15. **`nprocs : int, optional`**
   - Number of r.neighbor processes to run in parallel
   - Default: 1

16. **`flags : str, optional`**
   - Allowed values: c, e, n, r
   - c
   - Use circular neighborhood
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.neighbors.html#__tabbed_2_3) for all details)*

17. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

18. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

19. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

20. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 20 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.neighbors.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast.neighbors performs r.neighbors computations
on the maps of a space time raster dataset (STRDS). This module supports
the options that are available in r.neighbors .

The user must provide an input and an output space time raster dataset
and the basename of the resulting raster maps. The resulting STRDS will
have the same temporal resolution as the input dataset. With the -e flag, resulting maps can be registered in an existing STRDS, that e.g.
may have been created with a previous run of t.rast.neighbors . All
maps will be processed using the current region settings unless the -r flag is selected. In the latter case, the computaional region is
set to each raster map selected from the input STRDS.

The user can select a subset of the input space time raster dataset for
processing using a SQL WHERE statement or using the region_relation for spatial selection of raster maps. For the spatial map selection the
current computational region is used, even when the -r flag is
given. The number of CPU's to be used for parallel processing can be
specified with the nprocs option to speedup the computation on
multi-core system.

Semantic labels are needed to relate output raster maps to input raster
maps. E.g. with method=stddev , the user needs to know the spatial
extent, the time stamp and the semantic label to determine which stddev
map corresponds to which input map.

---

## See Also

Related tools:
- [`r.neighbors`](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)
- [`t.rast.aggregate.ds`](https://grass.osgeo.org/grass-devel/manuals/t.rast.aggregate.ds.html)
- [`t.rast.extract`](https://grass.osgeo.org/grass-devel/manuals/t.rast.extract.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.mask`](https://grass.osgeo.org/grass-devel/manuals/r.mask.html)

---

## Resources

- [Official t.rast.neighbors manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.neighbors.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.neighbors.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
