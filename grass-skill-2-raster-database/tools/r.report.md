# r.report

**Category**: raster

## Description

Reports statistics for raster maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_report(map,units="cells,percent",output=None,null_value="*",page_length=0,page_width=79,nsteps=255,sort=None,format="plain",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | list[str], required`**
   - Name of raster map(s) to report on
   - Used as: input, raster, name

2. **`units : str | list[str], optional`**
   - Units to report
   - Allowed values: miles, meters, kilometers, acres, hectares, cells, percent
   - miles: area in square miles
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.report.html#__tabbed_2_3) for all details)*

3. **`output : str, optional`**
   - Name for output file to hold the report
   - If no output file given report is printed to standard output
   - Used as: output, file, name

4. **`null_value : str, optional`**
   - String representing NULL value
   - Used as: string
   - Default: *

5. **`page_length : int, optional`**
   - Page length
   - Default: 0

6. **`page_width : int, optional`**
   - Page width
   - Default: 79

7. **`nsteps : int, optional`**
   - Number of floating-point subranges to collect stats from
   - Default: 255

8. **`sort : str, optional`**
   - Sort output statistics by cell counts
   - Default: sorted by categories or intervals
   - Allowed values: asc, desc
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.report.html#__tabbed_2_3) for all details)*

9. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.report.html#__tabbed_2_3) for all details)*

10. **`flags : str, optional`**
   - Allowed values: h, f, e, n, a, c, i
   - h
   - Suppress page headers
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.report.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.report.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.report allows the user to set up a series of report parameters to be
applied to a raster map, and creates a report. The report will print out
to the standard output if output parameter is not given.
The report can be either formatted in a human-readable way (default) or in a
JSON format using the format=json parameter.

The report itself consists of two parts, a header section and the main
body of the report.

The header section of the report identifies the raster map(s) (by map
name and title), project, mapset, report date, and the region of
interest. The area of interest is described in two parts: the user's
current geographic region is presented, and the mask is presented (if
any is used).

The main body of the report consists of from one to three tables which
present the statistics for each category and the totals for each unit
column. Note that the statistics is always computed in the current
computational region.

When multiple (typically two) raster maps are specified,
cross-tabulation table for each combination of categories in the raster
maps will be computed and formatted in a human-readable way (see
example).

---

## See Also

Related tools:
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.coin`](https://grass.osgeo.org/grass-devel/manuals/r.coin.html)
- [`r.describe`](https://grass.osgeo.org/grass-devel/manuals/r.describe.html)
- [`r.info`](https://grass.osgeo.org/grass-devel/manuals/r.info.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)

---

## Authors

Michael Shapiro, U.S. Army Construction Engineering Research
Laboratory Sort option by Martin Landa, Czech Technical University in Prague, 2013

---

## Resources

- [Official r.report manual](https://grass.osgeo.org/grass-devel/manuals/r.report.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.report.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
