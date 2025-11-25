# g.manual

**Category**: general

## Description

Displays the manual pages of GRASS modules.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_manual(entry,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`entry : str, required`**
   - Manual entry to be displayed

2. **`flags : str, optional`**
   - Allowed values: i, t, m, o
   - i
   - Display index
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.manual.html#__tabbed_2_3) for all details)*

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

g.manual displays the manual pages of GRASS in HTML and MAN format.

---

## Resources

- [Official g.manual manual](https://grass.osgeo.org/grass-devel/manuals/g.manual.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.manual.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
