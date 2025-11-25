# t.upgrade

**Category**: temporal

## Description

Upgrades the version of the temporal database.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_upgrade(verbose=None,quiet=None,superquiet=None)
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

The t.upgrade module upgrades the temporal database in the current
mapset from version 2 (default in GRASS 7) to 3 (default in GRASS 8).
The version 3 introduces a semantic label support, see i.band.library for details.

---

## See Also

Related tools:
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Authors

Martin Landa and Markus Neteler

---

## Resources

- [Official t.upgrade manual](https://grass.osgeo.org/grass-devel/manuals/t.upgrade.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.upgrade.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
