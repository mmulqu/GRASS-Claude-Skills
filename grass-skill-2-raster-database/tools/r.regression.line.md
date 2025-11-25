# r.regression.line

**Category**: raster

## Description

Calculates linear regression from two raster maps: y = a + b*x.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_regression_line(mapx,mapy,output=None,format="plain",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`mapx : str | np.ndarray, required`**
   - Map for x coefficient
   - Used as: input, raster, name

2. **`mapy : str | np.ndarray, required`**
   - Map for y coefficient
   - Used as: input, raster, name

3. **`output : str, optional`**
   - ASCII file for storing regression coefficients (output to screen if file not specified).
   - Used as: output, file, name

4. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, shell, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.regression.line.html#__tabbed_2_3) for all details)*

5. **`flags : str, optional`**
   - Allowed values: g
   - g
   - Print in shell script style [deprecated]

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

r.regression.line calculates a linear regression from two raster maps,
according to the formula

where

represent the input raster maps.

Optionally, it saves regression coefficients as a ASCII file. The result
includes the following coefficients: offset/intercept (a) and gain/slope
(b), correlation coefficient (R), number of elements (N), means (medX,
medY), standard deviations (sdX, sdY), and the F test for testing the
significance of the regression model as a whole (F).

---

## See Also

Related tools:
- [`d.correlate`](https://grass.osgeo.org/grass-devel/manuals/d.correlate.html)
- [`r.regression.multi`](https://grass.osgeo.org/grass-devel/manuals/r.regression.multi.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)

---

## Authors

Dr. Agustin Lobo - alobo at ija.csic.es Updated to GRASS 5.7 Michael Barton, Arizona State University Script style output Markus Neteler Conversion to C module Markus Metz

---

## Resources

- [Official r.regression.line manual](https://grass.osgeo.org/grass-devel/manuals/r.regression.line.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.regression.line.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
