# d.erase

**Category**: display

## Description

Erases the contents of the active graphics display frame with user defined color.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_erase(bgcolor="white",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`bgcolor : str, optional`**
   - Background color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

2. **`flags : str, optional`**
   - Allowed values: f
   - f
   - Remove all frames and erase the screen

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

d.erase erases the contents of the active graphics frame, and replaces
it with the color black (by default) or by whatever color is specified
by the user.

---

## See Also

Related tools:
- [`d.mon`](https://grass.osgeo.org/grass-devel/manuals/d.mon.html)
- [`d.redraw`](https://grass.osgeo.org/grass-devel/manuals/d.redraw.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)
- [`d.vect`](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)

---

## Resources

- [Official d.erase manual](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.erase.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
