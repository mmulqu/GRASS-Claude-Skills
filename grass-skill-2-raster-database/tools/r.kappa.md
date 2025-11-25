# r.kappa

**Category**: raster

## Description

Calculates error matrix and kappa parameter for accuracy assessment of classification result.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_kappa(classification,reference,output=None,title="ACCURACY ASSESSMENT",format="plain",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`classification : str | np.ndarray, required`**
   - Name of raster map containing classification result
   - Used as: input, raster, name

2. **`reference : str | np.ndarray, required`**
   - Name of raster map containing reference classes
   - Used as: input, raster, name

3. **`output : str, optional`**
   - Name for output file containing error matrix and kappa
   - If not given write to standard output
   - Used as: output, file, name

4. **`title : str, optional`**
   - Title for error matrix and kappa
   - Default: ACCURACY ASSESSMENT

5. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.kappa.html#__tabbed_2_3) for all details)*

6. **`flags : str, optional`**
   - Allowed values: w, h, m
   - w
   - Wide report
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.kappa.html#__tabbed_2_3) for all details)*

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
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

r.kappa tabulates the error matrix of classification result by
crossing classified map layer with respect to reference map layer. Both
overall kappa (accompanied by its variance ) and conditional kappa values are calculated. This analysis program respects the current
geographic region and mask settings.

r.kappa calculates the error matrix of the two map layers and prepares
the table from which the report is to be created. kappa values for
overall and each classes are computed along with their variances. Also
percent of commission and omission error, total correct classified
result by pixel counts, total area in pixel counts and percentage of
overall correctly classified pixels are tabulated.

The report will be written to an output file which is in plain text
format and named by user at prompt of running the program. To obtain
machine readable version, specify a json output format.

The body of the report is arranged in panels. The classified result map
layer categories is arranged along the vertical axis of the table, while
the reference map layer categories along the horizontal axis. Each panel
has a maximum of 5 categories (9 if wide format) across the top. In
addition, the last column of the last panel reflects a cross total of
each column for each row. All of the categories of the map layer
arranged along the vertical axis, i.e., the reference map layer, are
included in each panel. There is a total at the bottom of each column
representing the sum of all the rows in that column.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.category`](https://grass.osgeo.org/grass-devel/manuals/r.category.html)
- [`r.mask`](https://grass.osgeo.org/grass-devel/manuals/r.mask.html)
- [`r.reclass`](https://grass.osgeo.org/grass-devel/manuals/r.reclass.html)
- [`r.report`](https://grass.osgeo.org/grass-devel/manuals/r.report.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)

---

## Authors

Tao Wen, University of Illinois at Urbana-Champaign, Illinois Maris Nartiss, University of Latvia (JSON output, MCC)

---

## Resources

- [Official r.kappa manual](https://grass.osgeo.org/grass-devel/manuals/r.kappa.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.kappa.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
