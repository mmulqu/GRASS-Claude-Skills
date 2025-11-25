# t.rast.mapcalc

**Category**: temporal

## Description

Performs spatio-temporal mapcalc expressions on temporally sampled maps of space time raster datasets.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_mapcalc(inputs,expression,method="equal",output,basename,nprocs=1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`inputs : str | list[str], required`**
   - Name of the input space time raster datasets
   - Used as: input, strds, name

2. **`expression : str, required`**
   - Spatio-temporal mapcalc expression

3. **`method : str | list[str], optional`**
   - The method to be used for sampling the input dataset
   - Used as: name
   - Allowed values: start, during, overlap, contain, equal, follows, precedes

4. **`output : str, required`**
   - Name of the output space time raster dataset
   - Used as: output, strds, name

5. **`basename : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Basename for output raster maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier
   - Used as: output, raster, basename

6. **`nprocs : int, optional`**
   - Number of r.mapcalc processes to run in parallel
   - Default: 1

7. **`flags : str, optional`**
   - Allowed values: n, s
   - n
   - Register Null maps
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.mapcalc.html#__tabbed_2_3) for all details)*

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.mapcalc.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast.mapcalc performs spatio-temporal mapcalc expressions on maps
of temporally sampled space time raster datasets (STRDS). Spatial and
temporal operators and internal variables are available in the
expression string. The description of the spatial operators, functions
and internal variables is available in the r.mapcalc manual page. The temporal functions are described in detail below.

This module expects several parameters. All space time raster datasets
that are referenced in the mapcalc expression must be listed in the inputs option. The first space time raster dataset that is listed
as input will be used to temporally sample all other space time raster
datasets. The temporal sampling method can be chosen using the method option. The order of the STRDS's in the mapcalc expression
can be different to the order of the STRDS's in the input option. The
resulting space time raster dataset must be specified in the output option together with the basename of generated raster maps that are
registered in the resulting STRDS. Empty maps resulting from
map-calculation are not registered by default. This behavior can be
changed with the -n flag. The flag -s can be used to assure that
only spatially related maps in the STRDS's are processed. Spatially
related means that temporally related maps overlap in their spatial
extent.

The module t.rast.mapcalc supports parallel processing. The option nprocs specifies the number of processes that can be started in
parallel.

A mapcalc expression must be provided to process the temporal sampled
maps. Temporal internal variables are available in addition to the r.mapcalc spatial operators and functions:

The supported internal variables for relative and absolute time are:

td() - This internal variable represents the size of the current
sample time interval in days and fraction of days for absolute time,
and in relative units in case of relative time.

start_time() - This internal variable represents the time difference
between the start time of the sample space time raster dataset and the start
time of the current sample interval or instance. The time is measured in days
and fraction of days for absolute time, and in relative units in case of
relative time.

end_time() - This internal variable represents the time difference between
the start time of the sample space time raster dataset and the end time of the
current sample interval. The time is measured in days and fraction of days for
absolute time, and in relative units in case of relative time. The end_time()
will be represented by null() in case of a time instance.

The supported internal variables for the current sample interval or instance for absolute time are:

The end_* functions are represented by the null() internal variable
in case of time instances.

---

## See Also

Related tools:
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`t.register`](https://grass.osgeo.org/grass-devel/manuals/t.register.html)
- [`t.rast.list`](https://grass.osgeo.org/grass-devel/manuals/t.rast.list.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.rast.mapcalc manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.mapcalc.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.mapcalc.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
