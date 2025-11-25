# d.rgb

**Category**: display

## Description

Displays three user-specified raster maps as red, green, and blue overlays in the active graphics frame.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_rgb(red,green,blue,flags=None,verbose=None,quiet=None,superquiet=None)
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

4. **`flags : str, optional`**
   - Allowed values: n
   - n
   - Make null cells opaque

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

d.rgb displays three user-specified raster maps as red, green, and
blue overlays in the active graphics frame.

RGB stands for red , green , and blue . d.rgb visually
combines three raster maps to form a color image. For each map, the
corresponding component from the layer's color table is used (e.g. for
the red layer, the red component is used, and so on). In general, the
input raster maps should use a grey-scale color table.

---

## See Also

Related tools:
- [`d.colortable`](https://grass.osgeo.org/grass-devel/manuals/d.colortable.html)
- [`d.his`](https://grass.osgeo.org/grass-devel/manuals/d.his.html)
- [`r.blend`](https://grass.osgeo.org/grass-devel/manuals/r.blend.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r.composite`](https://grass.osgeo.org/grass-devel/manuals/r.composite.html)

---

## Resources

- [Official d.rgb manual](https://grass.osgeo.org/grass-devel/manuals/d.rgb.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.rgb.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
