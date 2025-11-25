# r.out.ppm3

**Category**: raster

## Description

Converts 3 GRASS raster layers (R,G,B) to a PPM image file.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_out_ppm3(red,green,blue,output,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`red : str | np.ndarray, required`**
   - Name of raster map to be used for <red>
   - Used as: input, raster

2. **`green : str | np.ndarray, required`**
   - Name of raster map to be used for <green>
   - Used as: input, raster

3. **`blue : str | np.ndarray, required`**
   - Name of raster map to be used for <blue>
   - Used as: input, raster

4. **`output : str, required`**
   - Name for new PPM file. (use '-' for stdout)

5. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Add comments to describe the region

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

r.out.ppm3 converts 3 GRASS raster layers (R,G,B) to a PPM image
file, using the current region.

This program converts a GRASS raster map to a PPM image file using the
the current region settings.

To get the full area and resolution of the raster map, run:

before running r.out.ppm3 .

---

## See Also

Related tools:
- [`r.out.ppm`](https://grass.osgeo.org/grass-devel/manuals/r.out.ppm.html)
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`d.rgb`](https://grass.osgeo.org/grass-devel/manuals/d.rgb.html)

---

## Resources

- [Official r.out.ppm3 manual](https://grass.osgeo.org/grass-devel/manuals/r.out.ppm3.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.ppm3.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
