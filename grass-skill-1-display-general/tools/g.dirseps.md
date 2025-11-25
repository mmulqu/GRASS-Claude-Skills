# g.dirseps

**Category**: general

## Description

Internal GRASS utility for converting directory separator characters. Converts any directory separator characters in the input string to or from native host format, and writes the changed path to standard output. Useful in scripts for Windows compatibility.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_dirseps(path=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`path : str, optional`**
   - Path to be converted (read from stdin if not specified)

2. **`flags : str, optional`**
   - Allowed values: h, g
   - h
   - Convert directory separators to native host format
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.dirseps.html#__tabbed_2_3) for all details)*

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

g.dirseps is an internal tool only. It copies input string to stdout,
changing directory separator characters as specified by flags. It is
used for interoperability between Unix and MS-Windows pathnames.

---

## Resources

- [Official g.dirseps manual](https://grass.osgeo.org/grass-devel/manuals/g.dirseps.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.dirseps.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
