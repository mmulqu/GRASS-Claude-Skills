# g.version

**Category**: general

## Description

Displays GRASS version info. Optionally also prints build or copyright information.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_version(format="plain",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`format : str, optional`**
   - Output format
   - Used as: name
   - Allowed values: plain, shell, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.version.html#__tabbed_2_3) for all details)*

2. **`flags : str, optional`**
   - Allowed values: c, x, b, r, e, g
   - c
   - Print also the copyright message
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.version.html#__tabbed_2_3) for all details)*

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

g.version prints to standard output the GRASS version number, date,
the GRASS copyright ( -c flag), and GRASS build information
( -b flag).

---

## Authors

Michael Shapiro, U.S. Army Construction Engineering Research
Laboratory Extended info by Martin Landa, Czech Technical University in Prague,
Czech Republic

---

## Resources

- [Official g.version manual](https://grass.osgeo.org/grass-devel/manuals/g.version.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.version.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
