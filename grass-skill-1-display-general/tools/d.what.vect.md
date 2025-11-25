# d.what.vect

**Category**: display

## Description

Allows the user to interactively query vector map layers at user-selected locations.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_what_vect(map,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | list[str], required`**
   - Name of input vector map(s)
   - Or data source(s) for direct OGR access
   - Used as: input, vector, name

2. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

3. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

4. **`superquiet : bool, optional`**
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

d.what.vect outputs the category value(s) associated with
user-specified location(s) in user-specified vector map layer(s). The
active monitor can be selected with d.mon .

---

## See Also

Related tools:
- [`d.what.rast`](https://grass.osgeo.org/grass-devel/manuals/d.what.rast.html)
- [`d.redraw`](https://grass.osgeo.org/grass-devel/manuals/d.redraw.html)
- [`d.erase`](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)
- [`d.vect`](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)
- [`d.mon`](https://grass.osgeo.org/grass-devel/manuals/d.mon.html)

---

## Resources

- [Official d.what.vect manual](https://grass.osgeo.org/grass-devel/manuals/d.what.vect.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.what.vect.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
