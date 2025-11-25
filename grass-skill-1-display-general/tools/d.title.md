# d.title

**Category**: display

## Description

Create a TITLE for a raster map in a form suitable for display with d.text.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_title(map,color="black",size=4.0,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map
   - Used as: input, raster, name

2. **`color : str, optional`**
   - Sets the text color
   - Used as: color
   - Default: black

3. **`size : float, optional`**
   - Sets the text size as percentage of the frame's height
   - Allowed values: 0-100
   - Default: 4.0

4. **`flags : str, optional`**
   - Allowed values: d, f, s
   - d
   - Draw title on current display
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.title.html#__tabbed_2_3) for all details)*

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

d.title generates to standard output a string which can be used by d.text to draw a TITLE for the raster map layer name in
the active display frame on the graphics monitor. Output created by d.title can be redirected into a file, or piped directly into d.text to display the map TITLE created by d.title . The
map TITLE created will include the map layer's name, TITLE, MAPSET,
LOCATION_NAME, geographic region boundary coordinates, and cell
resolution. If the -d draw flag is used, then d.title will call d.text for you and the title will be automatically rendered to the
display.

---

## See Also

Related tools:
- [`d.font`](https://grass.osgeo.org/grass-devel/manuals/d.font.html)
- [`d.text`](https://grass.osgeo.org/grass-devel/manuals/d.text.html)

---

## Resources

- [Official d.title manual](https://grass.osgeo.org/grass-devel/manuals/d.title.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.title.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
