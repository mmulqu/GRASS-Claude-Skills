# d.rhumbline

**Category**: display

## Description

Displays the rhumbline joining two longitude/latitude coordinates.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_rhumbline(coordinates,line_color="black",verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`coordinates : tuple[float, float, float, float] | list[float] | str, required`**
   - Starting and ending coordinates
   - Used as: input, coords, lon1,lat1,lon2,lat2

2. **`line_color : str, optional`**
   - Line color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

3. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

4. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

5. **`superquiet : bool, optional`**
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

A rhumbline (loxodrome) is a line following a constant angle of the
compass (i.e., a line of constant direction). It crosses all meridians
at the same angle, i.e. a path of constant bearing. d.rhumbline displays the rhumbline joining any two user-specified points in the
active frame on the user's graphics monitor. The named coordinate
locations must fall within the boundaries of the user's current
geographic region.

The user has to specify the starting and ending longitude/latitude
coordinates of the rhumbline and (optionally) the color in which the
rhumbline will be displayed; in this case, the program will run
non-interactively.

---

## See Also

Related tools:
- [`d.geodesic`](https://grass.osgeo.org/grass-devel/manuals/d.geodesic.html)
- [`d.grid`](https://grass.osgeo.org/grass-devel/manuals/d.grid.html)
- [`m.measure`](https://grass.osgeo.org/grass-devel/manuals/m.measure.html)

---

## Resources

- [Official d.rhumbline manual](https://grass.osgeo.org/grass-devel/manuals/d.rhumbline.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.rhumbline.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
