# i.oif

**Category**: imagery

## Description

Calculates Optimum-Index-Factor table for spectral bands

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_oif(input,output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - Name of input raster map(s)
   - Used as: input, raster, name

2. **`output : str, optional`**
   - Name for output file (if omitted or "-" output to stdout)
   - Used as: output, file, name

3. **`flags : str, optional`**
   - Allowed values: g, s
   - g
   - Print in shell script style
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.oif.html#__tabbed_2_3) for all details)*

4. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

i.oif calculates the Optimum Index Factor for multi-spectral satellite
imagery.

The Optimum Index Factor (OIF) determines the three-band combination
that maximizes the variability (information) in a multi-spectral scene.
The index is a ratio of the total variance (standard deviation) within
and the correlation between all possible band combinations. The bands
that comprise the highest scoring combination from i.oif are used as
the three color channels required for d.rgb or r.composite .

The analysis is saved to a file in the current directory called
"i.oif.result".

---

## See Also

Related tools:
- [`d.rgb`](https://grass.osgeo.org/grass-devel/manuals/d.rgb.html)
- [`r.composite`](https://grass.osgeo.org/grass-devel/manuals/r.composite.html)
- [`r.covar`](https://grass.osgeo.org/grass-devel/manuals/r.covar.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)

---

## Authors

Markus Neteler, ITC-Irst, Trento, Italy Updated to GRASS 5.7 by Michael Barton, Arizona State University

---

## Resources

- [Official i.oif manual](https://grass.osgeo.org/grass-devel/manuals/i.oif.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.oif.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
