# d.his

**Category**: display

## Description

Displays the result obtained by combining hue, intensity, and saturation (HIS) values from user-specified input raster map layers.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_his(hue,intensity=None,saturation=None,brighten=0,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`hue : str | np.ndarray, required`**
   - Name of layer to be used for hue
   - Used as: input, raster

2. **`intensity : str | np.ndarray, optional`**
   - Name of layer to be used for intensity
   - Used as: input, raster

3. **`saturation : str | np.ndarray, optional`**
   - Name of layer to be used for saturation
   - Used as: input, raster

4. **`brighten : int, optional`**
   - Percent to brighten intensity channel
   - Allowed values: -99-99
   - Default: 0

5. **`flags : str, optional`**
   - Allowed values: n
   - n
   - Respect NULL values while drawing

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.his displays the result obtained by combining hue, intensity, and
saturation (HIS) values from user-specified input raster map layers.

HIS stands for hue, intensity, and saturation. This program produces a
raster map layer providing a visually pleasing combination of hue,
intensity, and saturation values from two or three user-specified raster
map layers.

The human brain automatically interprets the vast amount of visual
information available according to basic rules. Color, or hue , is used
to categorize objects. Shading, or intensity , is interpreted as
three-dimensional texturing. Finally, the degree of haziness, or saturation , is associated with distance or depth. This program allows
data from up to three raster map layers to be combined into an image
which retains the original information in terms of hue , intensity ,
and saturation .

---

## See Also

Related tools:
- [`d.colortable`](https://grass.osgeo.org/grass-devel/manuals/d.colortable.html)
- [`d.frame`](https://grass.osgeo.org/grass-devel/manuals/d.frame.html)
- [`d.rgb`](https://grass.osgeo.org/grass-devel/manuals/d.rgb.html)
- [`d.shade`](https://grass.osgeo.org/grass-devel/manuals/d.shade.html)
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r.his`](https://grass.osgeo.org/grass-devel/manuals/r.his.html)
- [`i.his.rgb`](https://grass.osgeo.org/grass-devel/manuals/i.his.rgb.html)
- [`i.rgb.his`](https://grass.osgeo.org/grass-devel/manuals/i.rgb.his.html)

---

## Resources

- [Official d.his manual](https://grass.osgeo.org/grass-devel/manuals/d.his.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.his.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
