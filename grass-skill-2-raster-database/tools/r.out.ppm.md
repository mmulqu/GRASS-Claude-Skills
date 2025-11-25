# r.out.ppm

**Category**: raster

## Description

Converts a GRASS raster map to a PPM image file.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_out_ppm(input,output="<rasterfilename>.ppm",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str, optional`**
   - Name for new PPM file (use '-' for stdout)
   - Used as: output, file, name
   - Default: <rasterfilename>.ppm

3. **`flags : str, optional`**
   - Allowed values: g, h
   - g
   - Output greyscale instead of color
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.out.ppm.html#__tabbed_2_3) for all details)*

4. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

r.out.ppm converts a GRASS raster map into a PPM image at the pixel
resolution of the CURRENTLY DEFINED REGION. To get the resolution and
region settings of the raster map, run:

before running r.out.ppm .

By default the PPM file created is 24-bit color, rawbits storage. You
can use the -g flag to force r.out.ppm to output an 8-bit
greyscale instead. The greyscale conversion uses the NTSC conversion:

One pixel is written for each cell value, so if ew_res and ns_res differ, the aspect ratio of the resulting image will be off.

---

## See Also

Related tools:
- [`d.out.file`](https://grass.osgeo.org/grass-devel/manuals/d.out.file.html)
- [`r.out.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.out.ascii.html)
- [`r.out.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.out.gdal.html)
- [`r.out.mpeg`](https://grass.osgeo.org/grass-devel/manuals/r.out.mpeg.html)
- [`r.out.png`](https://grass.osgeo.org/grass-devel/manuals/r.out.png.html)
- [`r.out.ppm3`](https://grass.osgeo.org/grass-devel/manuals/r.out.ppm3.html)

---

## Resources

- [Official r.out.ppm manual](https://grass.osgeo.org/grass-devel/manuals/r.out.ppm.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.ppm.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
