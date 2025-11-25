# d.where

**Category**: display

## Description

Identifies the geographic coordinates associated with point locations given in display coordinates.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_where(at=None,input=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`at : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - Display coordinates to convert
   - Used as: x,y

2. **`input : str | io.StringIO, optional`**
   - File from which to read coordinates ("-" to read from stdin)
   - Used as: input, file, name

3. **`flags : str, optional`**
   - Allowed values: d, l, w, f
   - d
   - Output lat/long in decimal degree
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.where.html#__tabbed_2_3) for all details)*

4. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

5. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

6. **`superquiet : bool, optional`**
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

d.where is an interactive program that allows the user, using the
pointing device (mouse), to identify the geographic coordinates
associated with point locations within the current geographic region in
the active display frame on the graphics monitor.

Each mouse click will output the easting and northing of the point
currently located beneath the mouse pointer. A mouse-button menu is
presented so the user knows which mouse buttons to use. The output is
always printed to the terminal screen; if the output is redirected into
a file, it will be written to the file as well.

Mouse buttons:

The left mouse button prints the coordinates at the selected point, the
middle mouse button allows you to query two points (they are connected
by a line for convenience). Use the right mouse button to exit the
module.

---

## See Also

Related tools:
- [`d.what.rast`](https://grass.osgeo.org/grass-devel/manuals/d.what.rast.html)
- [`d.what.vect`](https://grass.osgeo.org/grass-devel/manuals/d.what.vect.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`v.what.rast`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html)
- [`v.what.vect`](https://grass.osgeo.org/grass-devel/manuals/v.what.vect.html)

---

## Authors

James Westervelt, Michael Shapiro, U.S. Army Construction Engineering Research Laboratory

---

## Resources

- [Official d.where manual](https://grass.osgeo.org/grass-devel/manuals/d.where.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.where.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
