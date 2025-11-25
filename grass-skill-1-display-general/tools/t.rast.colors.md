# t.rast.colors

**Category**: temporal

## Description

Creates/modifies the color table associated with each raster map of the space time raster dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_colors(input,color=None,raster=None,raster_3d=None,rules=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`color : str, optional`**
   - Name of color table (see r.color help)
   - Used as: input, colortable, style
   - Allowed values: aspect, aspectcolr, bcyr, bgyr, blues, byg, byr, celsius, corine, curvature, differences, elevation, etopo2, evi, fahrenheit, forest_cover, gdd, grass, greens, grey, grey.eq, grey.log, grey1.0, grey255, gyr, haxby, inferno, kelvin, magma, ndvi, ndwi, nlcd, oranges, plasma, population, population_dens, precipitation, precipitation_daily, precipitation_monthly, rainbow, ramp, random, reds, roygbiv, rstcurv, ryb, ryg, sepia, slope, soilmoisture, srtm, srtm_percent, srtm_plus, terrain, viridis, water, wave
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.colors.html#__tabbed_2_3) for all details)*

3. **`raster : str | np.ndarray, optional`**
   - Raster map from which to copy color table
   - Used as: input, raster, name

4. **`raster_3d : str, optional`**
   - 3D raster map from which to copy color table
   - Used as: input, raster_3d, name

5. **`rules : str | io.StringIO, optional`**
   - Path to rules file
   - Used as: input, file, name

6. **`flags : str, optional`**
   - Allowed values: r, w, l, n, g, a, e
   - r
   - Remove existing color table
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.colors.html#__tabbed_2_3) for all details)*

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

t.rast.colors computes a color table based on all registered maps of a
space time raster dataset and to assign this color table to each map.
Hence the created color table reflects the data range of the space time
raster dataset. This module is a simple wrapper around r.colors . All options of r.colors are supported.
Internally a file with map names is created and passed to the file option of r.colors .

Please have a look at the r.colors manual page for
further information.

---

## See Also

Related tools:
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)

---

## Resources

- [Official t.rast.colors manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.colors.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.colors.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
