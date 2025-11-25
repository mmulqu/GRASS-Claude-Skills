# t.rast.accdetect

**Category**: temporal

## Description

Detects accumulation patterns in temporally accumulated space time raster datasets created by t.rast.accumulate.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_accdetect(input,minimum=None,maximum=None,occurrence,indicator=None,start,stop=None,cycle,offset=None,basename,suffix="gran",range=None,staend="1,2,3",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`minimum : str, optional`**
   - Input space time raster dataset that specifies the minimum values to detect the accumulation pattern
   - Used as: input, strds, name

3. **`maximum : str, optional`**
   - Input space time raster dataset that specifies the maximum values to detect the accumulation pattern
   - Used as: input, strds, name

4. **`occurrence : str, required`**
   - The output space time raster dataset that stores the occurrence of the accumulation pattern using the provided data range
   - Used as: output, strds, name

5. **`indicator : str, optional`**
   - The output space time raster dataset that stores the indication of the start, intermediate and end of the specified data range
   - Used as: output, strds, name

6. **`start : str, required`**
   - The temporal starting point to begin the accumulation, eg '2001-01-01'

7. **`stop : str, optional`**
   - The temporal date to stop the accumulation, eg '2009-01-01'

8. **`cycle : str, required`**
   - The temporal cycle to restart the accumulation, eg '12 months'

9. **`offset : str, optional`**
   - The temporal offset to the begin of the next cycle, eg '6 months'

10. **`basename : str, required`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier

11. **`suffix : str, optional`**
   - Suffix to add at basename: set 'gran' for granularity, 'time' for the full time format, 'count' for numerical suffix with a specific number of digits (default %05)
   - Default: gran

12. **`range : tuple[float, float] | list[float] | str, optional`**
   - The minimum and maximum value of the occurrence of accumulated values, these values will be used if the min/max space time raster datasets are not specified
   - Used as: min,max

13. **`staend : tuple[int, int, int] | list[int] | str, optional`**
   - The user defined values that indicate start, intermediate and end status in the indicator output space time raster dataset
   - Used as: start,intermediate,end
   - Default: 1,2,3

14. **`flags : str, optional`**
   - Allowed values: n, r
   - n
   - Register empty maps in the output space time raster dataset, otherwise they will be deleted
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.accdetect.html#__tabbed_2_3) for all details)*

15. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

16. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

17. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

18. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 18 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.accdetect.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast.accdetect is designed to detect accumulation pattern in
temporally accumulated space time raster datasets created by t.rast.accumulate . This module's input is a
space time raster dataset resulting from a t.rast.accumulate run.

The start time and the end time of the pattern detection process
must be set, eg. start="2000-03-01" end="2011-01-01" . The start and end time do not need to be the same as for the accumulation run
that produced the input space time raster dataset. In addition a cycle , eg. "8 months", can be specified, that defines after which
time interval the accumulation pattern detection process restarts. The offset option specifies the time that should be skipped between two
cycles, eg. "4 months". The cycle and offset options must be
exactly the same that were used in the accumulation process that
generated the input space time raster dataset, otherwise the
accumulation pattern detection will produce wrong results.

The minimum and maximum values for the pattern detection process
can be set either by using space time raster datasets or by using fixed
values for all raster cells and time steps.

Using space time raster datasets allows specifying minimum and maximum
values for each raster cell and each time step. For example, we want to
detect the germination (minimum value) and harvesting (maximum value)
dates for different crops in Germany using the growing-degree-day (GDD)
method for several years. Different crops may grow in different raster
cells and change with time because of crop rotation. Hence we need to
specify different GDD germination/harvesting (minimum/maximum) values
for different raster cells and different years.

The raster maps that specify the minimum and maximum values of the
actual granule will be detected using the following temporal relations:
equals, during, overlaps, overlapped and contains. First, all maps with
time stamps equal to the current granule of the input STRDS will be
detected, the first minimum map and the first maximum map that are found
will be used as range definitions. If no equal maps are found, then maps
with a temporal during relation will be detected, then maps that
temporally overlap the actual granules and finally, maps that have a
temporal contain relation will be detected. If no maps are found or
minimum/maximum STRDS are not set, then the range option is used,
eg. range=480,730 .

The base name of of the generated maps must always be set.

This module produces two output space time raster datasets: occurrence
and indicator. The occurrence output STRDS stores the time in days
from the beginning of a given cycle for each raster cell and time step
that has a value within the minimum and maximum definition. These values
can be used to compute the duration of the recognized accumulation
pattern. The indicator output STRDS uses three integer values to
mark raster cells as beginning, intermediate state or end of an
accumulation pattern. By default, the module uses 1 to indicate the
start, 2 for the intermediate state and 3 to mark the end of the
accumulation pattern in a cycle. These default values can be changed
using the staend option.

---

## See Also

Related tools:
- [`t.rast.accumulate`](https://grass.osgeo.org/grass-devel/manuals/t.rast.accumulate.html)
- [`t.rast.aggregate`](https://grass.osgeo.org/grass-devel/manuals/t.rast.aggregate.html)
- [`t.rast.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/t.rast.mapcalc.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`r.series.accumulate`](https://grass.osgeo.org/grass-devel/manuals/r.series.accumulate.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)

---

## Resources

- [Official t.rast.accdetect manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.accdetect.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.accdetect.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
