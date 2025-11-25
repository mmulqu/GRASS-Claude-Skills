# d.fontlist

**Category**: display

## Description

Lists the available fonts.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_fontlist(flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`flags : str, optional`**
   - Allowed values: l, v
   - l
   - List fonts (default; provided for compatibility with d.font)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.fontlist.html#__tabbed_2_3) for all details)*

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

d.fontlist outputs a list of available fonts for use with GRASS
display commands.

---

## See Also

Related tools:
- [`d.text`](https://grass.osgeo.org/grass-devel/manuals/d.text.html)

---

## Resources

- [Official d.fontlist manual](https://grass.osgeo.org/grass-devel/manuals/d.fontlist.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.fontlist.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
