# r.rgb

**Category**: raster

## Description

Splits a raster map into red, green and blue maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_rgb(input,red=None,green=None,blue=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`red : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Red channel raster map name
   - Used as: output, raster, name

3. **`green : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Green channel raster map name
   - Used as: output, raster, name

4. **`blue : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Blue channel raster map name
   - Used as: output, raster, name

5. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.rgb generates separate red, green and blue maps from a raster map
and its associated color table (grey255).

---

## See Also

Related tools:
- [`r.composite`](https://grass.osgeo.org/grass-devel/manuals/r.composite.html)
- [`r.blend`](https://grass.osgeo.org/grass-devel/manuals/r.blend.html)
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)

---

## Resources

- [Official r.rgb manual](https://grass.osgeo.org/grass-devel/manuals/r.rgb.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.rgb.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
