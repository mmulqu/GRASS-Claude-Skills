# r.his

**Category**: raster

## Description

Generates red, green and blue (RGB) raster map layers combining hue, intensity and saturation (HIS) values from user-specified input raster map layers.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_his(hue,intensity=None,saturation=None,red,green,blue,bgcolor=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

4. **`red : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name of output layer to be used for red
   - Used as: output, raster

5. **`green : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name of output layer to be used for green
   - Used as: output, raster

6. **`blue : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name of output layer to be used for blue
   - Used as: output, raster

7. **`bgcolor : str, optional`**
   - Color to use instead of NULL values
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

8. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Use colors from color tables for NULL values

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.his.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

HIS stands for hue, intensity, and saturation. r.his produces red,
green and blue raster map layers providing a visually pleasing
combination of hue, intensity, and saturation values from two or three
user-specified raster map layers.

The human brain automatically interprets the vast amount of visual
information available according to basic rules. Color, or hue , is used
to categorize objects. Shading, or intensity , is interpreted as
three-dimensional texturing. Finally, the degree of haziness, or saturation , is associated with distance or depth. This program allows
data from up to three raster map layers to be combined into a color
image (in the form of separate red, green and blue raster map layers)
which retains the original information in terms of hue , intensity ,
and saturation .

While any raster map layer can be used to represent the hue information,
map layers with a few very distinct colors work best. Only raster map
layers representing continuously varying data like elevation, aspect,
weights, intensities, or amounts can suitably be used to provide
intensity and saturation information.

For example, a visually pleasing image can be made by using a watershed
map for the hue factor, an aspect map for the intensity factor, and
an elevation map for saturation . (The user may wish to leave out the
elevation information for a first try.) Ideally, the resulting image
should resemble the view from an aircraft looking at a terrain on a
sunny day with a bit of haze in the valleys.

Each map cell is processed individually. First, the working color is set
to the color of the corresponding cell in the map layer chosen to
represent hue . Second, this color is multiplied by the red intensity
of that cell in the intensity map layer. This map layer should have an
appropriate gray-scale color table associated with it. You can ensure
this by using the color manipulation capabilities of r.colors . Finally, the color is made somewhat
gray-based on the red intensity of that cell in the saturation map
layer. Again, this map layer should have a gray-scale color table
associated with it.

---

## See Also

Related tools:
- [`d.his`](https://grass.osgeo.org/grass-devel/manuals/d.his.html)
- [`d.colortable`](https://grass.osgeo.org/grass-devel/manuals/d.colortable.html)
- [`d.rgb`](https://grass.osgeo.org/grass-devel/manuals/d.rgb.html)
- [`r.blend`](https://grass.osgeo.org/grass-devel/manuals/r.blend.html)
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r.composite`](https://grass.osgeo.org/grass-devel/manuals/r.composite.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.shade`](https://grass.osgeo.org/grass-devel/manuals/r.shade.html)
- [`i.his.rgb`](https://grass.osgeo.org/grass-devel/manuals/i.his.rgb.html)
- [`i.rgb.his`](https://grass.osgeo.org/grass-devel/manuals/i.rgb.his.html)

---

## Resources

- [Official r.his manual](https://grass.osgeo.org/grass-devel/manuals/r.his.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.his.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
