# d.colortable

**Category**: display

## Description

Displays the color table associated with a raster map layer.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_colortable(map,color="white",lines=None,columns=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map whose color table is to be displayed
   - Used as: input, raster, name

2. **`color : str, optional`**
   - Color of lines separating the colors of the color table
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

3. **`lines : int, optional`**
   - Number of lines to appear in the color table
   - Allowed values: 1-1000

4. **`columns : int, optional`**
   - Number of columns to appear in the color table
   - Allowed values: 1-1000

5. **`flags : str, optional`**
   - Allowed values: n
   - n
   - Do not draw a collar showing the NULL color in FP maps

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

d.colortable is used to display the color table associated with a
raster map in the active frame on the graphics monitor. The map name
should be an available raster map in the user's current mapset search
path and location.

If the values of both lines and columns are not specified by
the user, d.colortable divides the active frame equally among the
number of categories present in the named raster map. If one option is
specified, the other is automatically set to accommodate all categories.
If both are specified, as many categories as possible are displayed.

If the user specifies the name of a map on the command line but does not
specify the values of other parameters, parameter default values will be
used. Alternately, if the user types simply d.colortable on the
command line without any program arguments, the program will prompt the
user for parameter settings using the standard GRASS parser interface.

---

## See Also

Related tools:
- [`d.erase`](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)
- [`d.legend`](https://grass.osgeo.org/grass-devel/manuals/d.legend.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)

---

## Resources

- [Official d.colortable manual](https://grass.osgeo.org/grass-devel/manuals/d.colortable.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.colortable.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
