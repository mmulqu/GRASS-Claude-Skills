# d.redraw

**Category**: display

## Description

Redraws the content of currently selected monitor.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_redraw(verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

2. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

3. **`superquiet : bool, optional`**
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

d.redraw redraws the content of the currently selected monitor. The
active monitor can be selected with d.mon .

---

## See Also

Related tools:
- [`d.erase`](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)
- [`d.vect`](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)
- [`d.mon`](https://grass.osgeo.org/grass-devel/manuals/d.mon.html)

---

## Resources

- [Official d.redraw manual](https://grass.osgeo.org/grass-devel/manuals/d.redraw.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.redraw.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
