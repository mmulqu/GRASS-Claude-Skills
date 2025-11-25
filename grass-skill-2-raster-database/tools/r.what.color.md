# r.what.color

**Category**: raster

## Description

Queries colors for a raster map layer.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_what_color(input,value=None,format="%d:%d:%d",color_format="hex",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`value : float | list[float] | str, optional`**
   - Values to query colors for

3. **`format : str, optional`**
   - Output format ('plain', 'json', or printf-style string)
   - Output format printf-style is deprecated, use 'color_format' option instead.
   - Default: %d:%d:%d

4. **`color_format : str, required`**
   - Color format
   - Color format for output values. Applies only when format is set to 'plain' or 'json'.
   - Used as: name
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.what.color.html#__tabbed_2_3) for all details)*

5. **`flags : str, optional`**
   - Allowed values: i
   - i
   - Read values from stdin

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
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

r.what.color outputs the color associated with user-specified category
values in a raster input map.

Values may be specified either using the value= option, or by
specifying the -i flag and passing the values on stdin , one per
line.

For each specified value, an output will be generated consisting of the
category value along with the color, e.g.:

Similarly, other color_format options available with format=json and format=plain are hex , hsv , triplet , and rgb , with hex being the
default color format.

If the input map is an integer (CELL) map, the category will be written
as an integer (no decimal point), otherwise it will be written in
floating point format ( printf("%.15g") format).

If the lookup fails for a value, the color will be output as an
asterisk (or as null in JSON), e.g.:

If a value cannot be parsed, both the value and the color will be output
as an asterisk (or as null in JSON), e.g.:

The format can be changed using the format= option. The value should
be a printf() -style format string containing three conversion
specifiers for the red, green and blue values respectively, e.g.:

If your system supports the %m\$ syntax, you can change the ordering
of the components, e.g.:

Common formats:

NOTE:

Please note that the printf() -style output format is deprecated and will be
removed in a future release. Use the color_format option instead,
together with format=plain or format=json .

---

## See Also

Related tools:
- [`r.what`](https://grass.osgeo.org/grass-devel/manuals/r.what.html)

---

## Resources

- [Official r.what.color manual](https://grass.osgeo.org/grass-devel/manuals/r.what.color.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.what.color.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
