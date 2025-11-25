# r.coin

**Category**: raster

## Description

Tabulates the mutual occurrence (coincidence) of categories for two raster map layers.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_coin(first,second,units,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`first : str | np.ndarray, required`**
   - Name of first input raster map
   - Used as: input, raster, name

2. **`second : str | np.ndarray, required`**
   - Name of second input raster map
   - Used as: input, raster, name

3. **`units : str, required`**
   - Unit of measure
   - c(ells), p(ercent), x(percent of category [column]), y(percent of category [row]), a(cres), h(ectares), k(square kilometers), m(square miles)
   - Allowed values: c, p, x, y, a, h, k, m

4. **`flags : str, optional`**
   - Allowed values: w
   - w
   - Wide report, 132 columns (default: 80)

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.coin tabulates the mutual occurrence of two raster map layers'
categories with respect to one another. This analysis program respects
the current geographic region and mask settings.

r.coin tabulates the coincidence of category values among the two map
layers and prepares the basic table from which the report is to be
created. This tabulation is followed by an indication of how long the
coincidence table will be. If the table is extremely long, the user may
decide that viewing it is not so important after all, and may cancel the
request at this point. Assuming the user continues, r.coin then allows
the user to choose one of eight units of measure in which the report
results can be given. These units are:

Note that three of these options give results as percentage values: "p"
is based on the grand total number of cells; "x" is based on only column
totals; and "y" is based on only row totals. Only one unit of measure
can be selected per report output. Type in just one of the letters
designating a unit of measure followed by a \<RETURN>. The report will
be printed to the screen for review. After reviewing the report on the
screen, the user is given several options. The report may be saved to a
file and/or sent to a printer. If printed, it may be printed with either
80 or 132 columns. Finally, the user is given the option to rerun the
coincidence tabulation using a different unit of measurement.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.category`](https://grass.osgeo.org/grass-devel/manuals/r.category.html)
- [`r.describe`](https://grass.osgeo.org/grass-devel/manuals/r.describe.html)
- [`r.reclass`](https://grass.osgeo.org/grass-devel/manuals/r.reclass.html)
- [`r.report`](https://grass.osgeo.org/grass-devel/manuals/r.report.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)

---

## Authors

Michael O'Shea, Michael Shapiro, U.S. Army Construction Engineering Research Laboratory

---

## Resources

- [Official r.coin manual](https://grass.osgeo.org/grass-devel/manuals/r.coin.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.coin.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
