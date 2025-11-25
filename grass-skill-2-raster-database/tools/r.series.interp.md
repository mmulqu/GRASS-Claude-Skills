# r.series.interp

**Category**: raster

## Description

Interpolates raster maps located (temporal or spatial) in between input raster maps at specific sampling positions.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_series_interp(input=None,datapos=None,infile=None,output=None,samplingpos=None,outfile=None,method="linear",overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], optional`**
   - Name of input raster map(s)
   - Used as: input, raster, name

2. **`datapos : float | list[float] | str, optional`**
   - Data point position for each input map

3. **`infile : str | io.StringIO, optional`**
   - Input file with one input raster map name and data point position per line, field separator between name and sample point is |
   - Used as: input, file, name

4. **`output : str | list[str], optional`**
   - Name for output raster map
   - Used as: output, raster, name

5. **`samplingpos : float | list[float] | str, optional`**
   - Sampling point position for each output map

6. **`outfile : str | io.StringIO, optional`**
   - Input file with one output raster map name and sample point position per line, field separator between name and sample point is |
   - Used as: input, file, name

7. **`method : str, optional`**
   - Interpolation method, currently only linear interpolation is supported
   - Allowed values: linear
   - Default: linear

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.series.interp.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.series.interp interpolates new raster maps located temporal or
spatial in between existing raster maps. The interpolation is performed
at specific sampling positions. The sampling position for each output
map must be specified, as well as the data position of the input maps.
The following interpolation methods are supported.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.series`](https://grass.osgeo.org/grass-devel/manuals/r.series.html)
- [`r.series.accumulate`](https://grass.osgeo.org/grass-devel/manuals/r.series.accumulate.html)

---

## Resources

- [Official r.series.interp manual](https://grass.osgeo.org/grass-devel/manuals/r.series.interp.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.series.interp.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
