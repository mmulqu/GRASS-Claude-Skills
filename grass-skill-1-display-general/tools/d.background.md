# d.background

**Category**: display

## Description

Fills the graphics display frame with user defined color.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_background(color,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`color : str, required`**
   - Background color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

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

d.background will fill the image (or generally display monitor) with a
single color specified by the color option.

---

## See Also

Related tools:
- [`d.erase`](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)

---

## Resources

- [Official d.background manual](https://grass.osgeo.org/grass-devel/manuals/d.background.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.background.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
