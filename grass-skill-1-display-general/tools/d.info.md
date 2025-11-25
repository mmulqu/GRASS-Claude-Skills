# d.info

**Category**: display

## Description

Displays information about the active display monitor. Display monitors are maintained by d.mon.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_info(flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`flags : str, optional`**
   - Allowed values: r, d, f, e, b, g
   - r
   - Display screen rectangle (left, right, top, bottom)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.info.html#__tabbed_2_3) for all details)*

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

d.info displays information about the active display monitor. Display
monitors are maintained by d.mon .

---

## See Also

Related tools:
- [`d.mon`](https://grass.osgeo.org/grass-devel/manuals/d.mon.html)
- [`d.vect`](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)

---

## Resources

- [Official d.info manual](https://grass.osgeo.org/grass-devel/manuals/d.info.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.info.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
