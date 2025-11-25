# i.rgb.his

**Category**: imagery

## Description

Transforms raster maps from RGB (Red-Green-Blue) color space to HIS (Hue-Intensity-Saturation) color space.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_rgb_his(red,green,blue,hue,intensity,saturation,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`red : str | np.ndarray, required`**
   - Name of input raster map (red)
   - Used as: input, raster, name

2. **`green : str | np.ndarray, required`**
   - Name of input raster map (green)
   - Used as: input, raster, name

3. **`blue : str | np.ndarray, required`**
   - Name of input raster map (blue)
   - Used as: input, raster, name

4. **`hue : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map (hue)
   - Used as: output, raster, name

5. **`intensity : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map (intensity)
   - Used as: output, raster, name

6. **`saturation : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map (saturation)
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

i.rgb.his is an image processing program that processes three input
raster map layers as red, green, and blue components and produces three
output raster map layers representing the hue, intensity, and saturation
of the data. The output raster map layers are created by a standard
red-green-blue (RGB) to hue-intensity-saturation (HIS) color
transformation. Each output raster map layer is given a linear gray
scale color table. The current geographic region definition and mask
settings are respected.

---

## See Also

Related tools:
- [`i.his.rgb`](https://grass.osgeo.org/grass-devel/manuals/i.his.rgb.html)

---

## Resources

- [Official i.rgb.his manual](https://grass.osgeo.org/grass-devel/manuals/i.rgb.his.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.rgb.his.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
