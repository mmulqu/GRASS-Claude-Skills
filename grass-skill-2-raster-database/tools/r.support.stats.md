# r.support.stats

**Category**: raster

## Description

Update raster map statistics

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_support_stats(map,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map
   - Used as: input, raster, name

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

r.support.stats allows the user to update raster map statistics
information.

---

## Authors

Micharl Shapiro, CERL: Original author Brad Douglas : GRASS 6 Port

---

## Resources

- [Official r.support.stats manual](https://grass.osgeo.org/grass-devel/manuals/r.support.stats.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.support.stats.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
