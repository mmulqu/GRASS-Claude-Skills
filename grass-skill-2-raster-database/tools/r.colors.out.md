# r.colors.out

**Category**: raster

## Description

Exports the color table associated with a raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_colors_out(map,rules=None,format="plain",color_format="hex",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map
   - Used as: input, raster, name

2. **`rules : str, optional`**
   - Path to output rules file
   - If not given write to standard output
   - Used as: output, file, name

3. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.colors.out.html#__tabbed_2_3) for all details)*

4. **`color_format : str, required`**
   - Color format
   - Color format for output values.
   - Used as: name
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.colors.out.html#__tabbed_2_3) for all details)*

5. **`flags : str, optional`**
   - Allowed values: p
   - p
   - Output values as percentages

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

r.colors.out allows the user to export the color table for a raster
map to a file which is suitable as input to r.colors .

Alternatively, the color rules can be exported as a JSON format
with format=json , to use them in other software.
The color format in JSON can be modified using the color_format parameter,
which includes the following options:

---

## See Also

Related tools:
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)

---

## Resources

- [Official r.colors.out manual](https://grass.osgeo.org/grass-devel/manuals/r.colors.out.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.colors.out.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
