# t.rast.accumulate

**Category**: temporal

## Description

Computes cyclic accumulations of a space time raster dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_accumulate(input,output,lower=None,upper=None,start,stop=None,cycle,offset=None,granularity="1 day",basename,suffix="gran",limits,scale=None,shift=None,method="mean",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`output : str, required`**
   - Name of the output space time raster dataset
   - Used as: output, strds, name

3. **`lower : str, optional`**
   - Input space time raster dataset that defines the lower threshold, values lower than this threshold are excluded from accumulation
   - Used as: input, strds, name

4. **`upper : str, optional`**
   - Input space time raster dataset that defines the upper threshold, values higher than this threshold are excluded from accumulation
   - Used as: input, strds, name

5. **`start : str, required`**
   - The temporal starting point to begin the accumulation, eg '2001-01-01'

6. **`stop : str, optional`**
   - The temporal date to stop the accumulation, eg '2009-01-01'

7. **`cycle : str, required`**
   - The temporal cycle to restart the accumulation, eg '12 months'

8. **`offset : str, optional`**
   - The temporal offset to the beginning of the next cycle, eg '6 months'

9. **`granularity : str, optional`**
   - The granularity for accumulation '1 day'
   - Default: 1 day

10. **`basename : str, required`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier

11. **`suffix : str, optional`**
   - Suffix to add to the basename. Set 'gran' for granularity, 'time' for the full time format, 'num' for numerical suffix with a specific number of digits (default %05)
   - Default: gran

12. **`limits : tuple[float, float] | list[float] | str, required`**
   - Use these limits in case lower and/or upper input space time raster datasets are not defined or contain NULL values
   - Used as: lower,upper

13. **`scale : float, optional`**
   - Scale factor for input space time raster dataset

14. **`shift : float, optional`**
   - Shift factor for input space time raster dataset

15. **`method : str, optional`**
   - This method will be applied to compute the accumulative values from the input maps in a single granule
   - Growing Degree Days or Winkler indices; Mean: sum(input maps)/(number of input maps); Biologically Effective Degree Days; Huglin Heliothermal index
   - Allowed values: mean, gdd, bedd, huglin

16. **`flags : str, optional`**
   - Allowed values: n, r
   - n
   - Register empty maps in the output space time raster dataset, otherwise they will be deleted
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.accumulate.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 20 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.accumulate.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast.accumulate is designed to perform temporal accumulations of
space time raster datasets. This module expects a space time raster
dataset as input that will be sampled by a given granularity . All
maps that have the start time during the actual granule will be
accumulated with the predecessor granule accumulation result using the
raster module r.series.accumulate . The default
granularity is 1 day, but any temporal granularity can be set.

The start time and the end time of the accumulation process must
be set, eg. start="2000-03-01" end="2011-01-01" . In addition, a cycle , eg. cycle="8 months" , can be specified, that defines
after which interval of time the accumulation process restarts. The offset option specifies the time that should be skipped between two
cycles, eg. offset="4 months" .

The lower and upper limits of the accumulation process can
be set, either by using space time raster datasets or by using fixed
values for all raster cells and time steps. The raster maps that specify
the lower and upper limits of the actual granule will be detected using
the following temporal relations: equals, during, overlaps, overlapped
and contains. First, all maps with time stamps equal to the current
granule will be detected, the first lower map and the first upper map
found will be used as limit definitions. If no equal maps are found,
then maps with a temporal during relation are detected, then maps that
temporally overlap the actual granules, until maps that have a temporal
contain relation are detected. If no maps are found or lower/upper STRDS
are not defined, then the limits option is used, eg. limits=10,30 .

The upper limit is only used in the Biologically Effective
Degree Days calculation.

The options shift , scale and method are passed to r.series.accumulate . Please refer to the
manual page of r.series.accumulate for
detailed option description.

The output is a new space time raster dataset with the provided
start time, end time and granularity containing the accumulated raster
maps. The base name of the generated maps must always be set. The output space time raster dataset can then be analyzed using t.rast.accdetect to detect specific accumulation
patterns.

---

## See Also

Related tools:
- [`t.rast.accdetect`](https://grass.osgeo.org/grass-devel/manuals/t.rast.accdetect.html)
- [`t.rast.aggregate`](https://grass.osgeo.org/grass-devel/manuals/t.rast.aggregate.html)
- [`t.rast.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/t.rast.mapcalc.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.series.accumulate`](https://grass.osgeo.org/grass-devel/manuals/r.series.accumulate.html)

---

## Resources

- [Official t.rast.accumulate manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.accumulate.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.accumulate.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
