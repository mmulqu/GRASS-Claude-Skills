# r.out.png

**Category**: raster

## Description

Export a GRASS raster map as a non-georeferenced PNG image.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_out_png(input,output,compression=6,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str, required`**
   - Name for new PNG file (use '-' for stdout)
   - Used as: output, file, name

3. **`compression : int, optional`**
   - Compression level of PNG file
   - (0 = none, 1 = fastest, 9 = best)
   - Allowed values: 0-9

4. **`flags : str, optional`**
   - Allowed values: t, w
   - t
   - Make NULL cells transparent
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.out.png.html#__tabbed_2_3) for all details)*

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.out.png exports a GRASS raster map in non-georeferenced Portable
Network Graphics (PNG) image format, respecting the current region
resolution and bounds.

Optionally the user can choose to export a World File (.wld) to provide
basic georeferencing support. When used with the transparency flag this
can create images useful for KML, TMS, or WMS overlays. (e.g. for use in
Google Earth or as OpenLayers tiles) If output is redirected to stdout,
the world file will be called png_map.wld .

---

## See Also

Related tools:
- [`r.out.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.out.gdal.html)
- [`r.out.ppm`](https://grass.osgeo.org/grass-devel/manuals/r.out.ppm.html)
- [`r.out.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.out.ascii.html)
- [`r.import`](https://grass.osgeo.org/grass-devel/manuals/r.import.html)

---

## Authors

Alex Shevlakov Hamish Bowman

---

## Resources

- [Official r.out.png manual](https://grass.osgeo.org/grass-devel/manuals/r.out.png.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.png.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
