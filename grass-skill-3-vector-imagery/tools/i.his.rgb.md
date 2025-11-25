# i.his.rgb

**Category**: imagery

## Description

Transforms raster maps from HIS (Hue-Intensity-Saturation) color space to RGB (Red-Green-Blue) color space.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_his_rgb(hue,intensity,saturation,red,green,blue,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`hue : str | np.ndarray, required`**
   - Name of input raster map (hue)
   - Used as: input, raster, name

2. **`intensity : str | np.ndarray, required`**
   - Name of input raster map (intensity)
   - Used as: input, raster, name

3. **`saturation : str | np.ndarray, required`**
   - Name of input raster map (saturation)
   - Used as: input, raster, name

4. **`red : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map (red)
   - Used as: output, raster, name

5. **`green : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map (green)
   - Used as: output, raster, name

6. **`blue : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map (blue)
   - Used as: output, raster, name

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
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

i.his.rgb is an image processing program that processes three input
raster map layers as hue, intensity and saturation components and
produces three output raster map layers representing the red, green and
blue components of this data. The output raster map layers are created
by a standard hue-intensity-saturation (HIS) to red-green-blue (RGB)
color transformation. Each output raster map layer is given a linear
gray scale color table. The current geographic region and mask settings
are respected.

---

## See Also

Related tools:
- [`i.rgb.his`](https://grass.osgeo.org/grass-devel/manuals/i.rgb.his.html)
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)

---

## Resources

- [Official i.his.rgb manual](https://grass.osgeo.org/grass-devel/manuals/i.his.rgb.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.his.rgb.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
