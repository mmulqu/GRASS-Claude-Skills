# i.colors.enhance

**Category**: imagery

## Description

Performs auto-balancing of colors for RGB images.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_colors_enhance(red,green,blue,strength=98,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`red : str | np.ndarray, required`**
   - Name of red channel
   - Used as: input, raster, name

2. **`green : str | np.ndarray, required`**
   - Name of green channel
   - Used as: input, raster, name

3. **`blue : str | np.ndarray, required`**
   - Name of blue channel
   - Used as: input, raster, name

4. **`strength : float, optional`**
   - Cropping intensity (upper brightness level)
   - Allowed values: 0-100
   - Default: 98

5. **`flags : str, optional`**
   - Allowed values: f, p, r, s
   - f
   - Extend colors to full range of data on each channel
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.colors.enhance.html#__tabbed_2_3) for all details)*

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

i.colors.enhance auto-balances and enhances the color channels of a
RGB image (e.g. from Landsat) to provide a more natural color mixture.
Only the color table of each image band is modified, the base data
remains untouched.

The module works by calculating a histogram for each color channel and
removing an adjustable amount of outliers from either end before
recalibrating the color scale with r.colors .

It will work with any 8-bit RGB imagery set and the script is easily
modified to work with other datasets of greater band-depth.

---

## See Also

Related tools:
- [`d.rgb`](https://grass.osgeo.org/grass-devel/manuals/d.rgb.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`i.oif`](https://grass.osgeo.org/grass-devel/manuals/i.oif.html)
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r.composite`](https://grass.osgeo.org/grass-devel/manuals/r.composite.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)

---

## Authors

Markus Neteler, Trento, Italy M. Hamish Bowman, Dept. Marine Science, Otago University, New Zealand

---

## Resources

- [Official i.colors.enhance manual](https://grass.osgeo.org/grass-devel/manuals/i.colors.enhance.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.colors.enhance.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
