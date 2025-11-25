# r.composite

**Category**: raster

## Description

Combines red, green and blue raster maps into a single composite raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_composite(red,green,blue,levels=32,level_red=None,level_green=None,level_blue=None,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`red : str | np.ndarray, required`**
   - Name of raster map to be used for <red>
   - Used as: input, raster, name

2. **`green : str | np.ndarray, required`**
   - Name of raster map to be used for <green>
   - Used as: input, raster, name

3. **`blue : str | np.ndarray, required`**
   - Name of raster map to be used for <blue>
   - Used as: input, raster, name

4. **`levels : int, optional`**
   - Number of levels to be used for each component
   - Allowed values: 1-256
   - Default: 32

5. **`level_red : int, optional`**
   - Number of levels to be used for <red>
   - Allowed values: 1-256

6. **`level_green : int, optional`**
   - Number of levels to be used for <green>
   - Allowed values: 1-256

7. **`level_blue : int, optional`**
   - Number of levels to be used for <blue>
   - Allowed values: 1-256

8. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

9. **`flags : str, optional`**
   - Allowed values: d, c
   - d
   - Dither
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.composite.html#__tabbed_2_3) for all details)*

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.composite.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

This program combines three raster maps to form a composite RGB map. For
each input map layer, the corresponding component from the map's color
table is used (e.g. for the red map, the red component is used, and so
on). In general, the maps should use a grey-scale color table.

---

## See Also

Related tools:
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)
- [`d.rgb`](https://grass.osgeo.org/grass-devel/manuals/d.rgb.html)
- [`r.blend`](https://grass.osgeo.org/grass-devel/manuals/r.blend.html)
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r.rgb`](https://grass.osgeo.org/grass-devel/manuals/r.rgb.html)

---

## Resources

- [Official r.composite manual](https://grass.osgeo.org/grass-devel/manuals/r.composite.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.composite.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
