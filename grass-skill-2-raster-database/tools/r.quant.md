# r.quant

**Category**: raster

## Description

Produces the quantization file for a floating-point map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_quant(input,rules=None,basemap=None,fprange=None,range=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - Raster map(s) to be quantized
   - Used as: input, raster

2. **`rules : str | io.StringIO, optional`**
   - Path to rules file ("-" to read from stdin)
   - Used as: input, file, name

3. **`basemap : str | np.ndarray, optional`**
   - Base map to take quant rules from
   - Used as: input, raster

4. **`fprange : tuple[str, str] | list[str] | str, optional`**
   - Floating point range: dmin,dmax
   - Used as: dmin,dmax

5. **`range : tuple[str, str] | list[str] | str, optional`**
   - Integer range: min,max
   - Used as: min,max

6. **`flags : str, optional`**
   - Allowed values: t, r
   - t
   - Truncate floating point data
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.quant.html#__tabbed_2_3) for all details)*

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

r.quant produces the quantization file for a floating-point map.

The map parameter defines the map for which the rules are to be
created. If more than one map is specified, then this implies that the
floating-point range is the minimum and maximum of all the maps
together, unless either basemap=map or fprange=min,max is specified.

The quant rules have to be entered interactively.

If rules is specified, the input has the form:

where value1 and value2 are floating point values and cat1 and cat2 are integers. If cat2 is missing, it is taken to be equal to cat1 . All values can be "*" which means infinity.

---

## Note

It is an error to specify both basemap and fprange .

---

## See Also

Related tools:
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)
- [`r.null`](https://grass.osgeo.org/grass-devel/manuals/r.null.html)

---

## Authors

Michael Shapiro, Olga Waupotitsch, U.S.Army Construction Engineering
Research Laboratory

---

## Resources

- [Official r.quant manual](https://grass.osgeo.org/grass-devel/manuals/r.quant.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.quant.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
