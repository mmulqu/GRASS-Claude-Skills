# v.colors.out

**Category**: vector

## Description

Exports the color table associated with a vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_colors_out(map,layer="1",rules=None,column=None,format="plain",color_format="hex",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`rules : str, optional`**
   - Path to output rules file
   - If not given write to standard output
   - Used as: output, file, name

4. **`column : str, optional`**
   - Name of attribute (numeric) column to which refer color rules
   - If not given, color rules refer to categories
   - Used as: input, dbcolumn, name

5. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.colors.out.html#__tabbed_2_3) for all details)*

6. **`color_format : str, required`**
   - Color format
   - Color format for output values.
   - Used as: name
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.colors.out.html#__tabbed_2_3) for all details)*

7. **`flags : str, optional`**
   - Allowed values: p
   - p
   - Output values as percentages

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.colors.out.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.colors.out allows the user to export the color table for a vector
map to a file which is suitable as input to v.colors .

Alternatively, the color rules can be exported as a JSON format
with format=json , to use them in other software.
The color format in JSON can be modified using the color_format parameter,
which includes the following options:

---

## See Also

Related tools:
- [`v.colors`](https://grass.osgeo.org/grass-devel/manuals/v.colors.html)
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r3.colors`](https://grass.osgeo.org/grass-devel/manuals/r3.colors.html)
- [`r.colors.out`](https://grass.osgeo.org/grass-devel/manuals/r.colors.out.html)
- [`r3.colors.out`](https://grass.osgeo.org/grass-devel/manuals/r3.colors.out.html)

---

## Resources

- [Official v.colors.out manual](https://grass.osgeo.org/grass-devel/manuals/v.colors.out.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.colors.out.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
