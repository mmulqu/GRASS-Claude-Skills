# d.profile

**Category**: display

## Description

Plots profile of a transect.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_profile(map,coordinates,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Raster map to be profiled
   - Used as: input, raster, name

2. **`coordinates : list[tuple[float, float]] | tuple[float, float] | list[float] | str, required`**
   - Profile coordinate pairs
   - Used as: input, coords, east,north

3. **`flags : str, optional`**
   - Allowed values: r
   - r
   - Use map's range recorded range

4. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

5. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

6. **`superquiet : bool, optional`**
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

d.profile displays the profile for a specified transect.

---

## See Also

Related tools:
- [`d.where`](https://grass.osgeo.org/grass-devel/manuals/d.where.html)
- [`r.profile`](https://grass.osgeo.org/grass-devel/manuals/r.profile.html)
- [`r.transect`](https://grass.osgeo.org/grass-devel/manuals/r.transect.html)

---

## Resources

- [Official d.profile manual](https://grass.osgeo.org/grass-devel/manuals/d.profile.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.profile.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
