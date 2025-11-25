# r.colors.stddev

**Category**: raster

## Description

Sets color rules based on stddev from a raster map's mean value.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_colors_stddev(map,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map
   - Used as: input, raster, name

2. **`flags : str, optional`**
   - Allowed values: b, z
   - b
   - Color using standard deviation bands
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.colors.stddev.html#__tabbed_2_3) for all details)*

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

r.colors.stddev set raster map color rules based on standard
deviations from a map's mean value, either as a continuous color
gradient or in color bands per standard deviation (S.D.) from the mean.

With the color band option values less that 1 S.D. from the mean are
colored green, within 1-2 S.D. are colored yellow, within 2-3 S.D. are
colored red, and beyond 3 S.D. are colored black.

For a differences map there is an option to lock the center of the color
table at zero. Values more than two S.D. below the mean will be colored
blue; values below the mean but less than 2 S.D. away will transition to
white, and above the mean the colors will similarly transition to full
red at +2 S.D.

---

## See Also

Related tools:
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)
- [`v.colors`](https://grass.osgeo.org/grass-devel/manuals/v.colors.html)

---

## Resources

- [Official r.colors.stddev manual](https://grass.osgeo.org/grass-devel/manuals/r.colors.stddev.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.colors.stddev.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
