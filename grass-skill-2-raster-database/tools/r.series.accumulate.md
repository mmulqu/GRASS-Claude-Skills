# r.series.accumulate

**Category**: raster

## Description

Makes each output cell value a accumulationfunction of the values assigned to the corresponding cells in the input raster map layers.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_series_accumulate(basemap=None,input=None,file=None,output,scale=1.0,shift=0.0,lower=None,upper=None,range=None,limits="10,30",method="gdd",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`basemap : str | np.ndarray, optional`**
   - Existing map to be added to output
   - Used as: input, raster, name

2. **`input : str | list[str], optional`**
   - Name of input raster map(s)
   - Used as: input, raster, name

3. **`file : str | io.StringIO, optional`**
   - Input file with raster map names, one per line
   - Used as: input, file, name

4. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

5. **`scale : float, optional`**
   - Scale factor for input
   - Default: 1.0

6. **`shift : float, optional`**
   - Shift factor for input
   - Default: 0.0

7. **`lower : str | np.ndarray, optional`**
   - The raster map specifying the lower accumulation limit, also called baseline
   - Used as: input, raster, name

8. **`upper : str | np.ndarray, optional`**
   - The raster map specifying the upper accumulation limit, also called cutoff. Only applied to BEDD computation.
   - Used as: input, raster, name

9. **`range : tuple[float, float] | list[float] | str, optional`**
   - Ignore values outside this range
   - Used as: min,max

10. **`limits : tuple[float, float] | list[float] | str, optional`**
   - Use these limits in case lower and/or upper input maps are not defined
   - Used as: lower,upper
   - Default: 10,30

11. **`method : str, optional`**
   - This method will be applied to compute the accumulative values from the input maps
   - Allowed values: gdd, bedd, huglin, mean
   - gdd: Growing Degree Days or Winkler indices
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.series.accumulate.html#__tabbed_2_3) for all details)*

12. **`flags : str, optional`**
   - Allowed values: n, z, f
   - n
   - Propagate NULLs
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.series.accumulate.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.series.accumulate.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.series.accumulate calculates (accumulated) raster value using
growing degree days (GDDs)/Winkler indices's, Biologically Effective
Degree Days (BEDD), Huglin heliothermal indices or an average approach
from several input maps for a given day. Accumulation of e.g.
degree-days to growing degree days (GDDs) can be done by providing a basemap with GDDs of the previous day.

The flag -a determines the average computation of the input raster
maps. In case the flag is not set, the average calculation is:

In case the flag was set, the calculation changes to arithmetic mean

GDD Growing Degree Days are calculated as

In case the -a is set, the Winkler indices are calculated instead of
GDD, usually accumulated for the period April 1st to October
31st (northern hemisphere) or the period October
1st to April 30t (southern hemisphere).

BEDDs Biologically Effective Degree Days are calculated as

with an optional upper cutoff applied to the average instead of the
temperature values.

The Huglin heliothermal index is calculated as

usually accumulated for the period April 1st to September
30th (northern hemisphere) or the period September
1st to April 30th (southern hemisphere).

Mean raster values are calculated as

For all the formulas min is the minimum value, max the maximum value
and average the average value. The min , max and average values
are automatically calculated from the input maps.

The shift and scale values are applied directly to the input values.
The lower and upper maps, as well as the range options are applied
to constrain the accumulation. In case the lower and upper maps are
not provided the limits option with default values will be applied.

If an existing map is provided with the basemap option, the values of
this map are added to the output.

---

## See Also

Related tools:
- [`g.list`](https://grass.osgeo.org/grass-devel/manuals/g.list.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.series`](https://grass.osgeo.org/grass-devel/manuals/r.series.html)
- [`r.series.interp`](https://grass.osgeo.org/grass-devel/manuals/r.series.interp.html)

---

## Authors

Markus Metz and Soeren Gebbert (based on r.series)

---

## Resources

- [Official r.series.accumulate manual](https://grass.osgeo.org/grass-devel/manuals/r.series.accumulate.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.series.accumulate.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
