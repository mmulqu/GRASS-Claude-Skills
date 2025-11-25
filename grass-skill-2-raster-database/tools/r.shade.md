# r.shade

**Category**: raster

## Description

Drapes a color raster over an shaded relief or aspect map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_shade(shade,color,output,brighten=0,bgcolor=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`shade : str | np.ndarray, required`**
   - Name of shaded relief or aspect raster map
   - Used as: input, raster, name

2. **`color : str | np.ndarray, required`**
   - Name of raster to drape over relief raster map
   - Typically, this raster is elevation or other colorful raster
   - Used as: input, raster, name

3. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name of shaded raster map
   - Used as: output, raster, name

4. **`brighten : int, optional`**
   - Percent to brighten
   - Allowed values: -99-99
   - Default: 0

5. **`bgcolor : str, optional`**
   - Color to use instead of NULL values
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

6. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Use colors from color tables for NULL values

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

r.shade will drape a color raster map over a shaded relief map. In
place of shaded relief, any raster map can be used including aspect or
slope. The color raster map is usually an elevation raster map with
colorful color table (as opposed to gray scale color table). However,
any raster map can be used including categorical raster maps. The result
is a raster map created from elevation and the shade raster.

Comparing to creating shaded relief as semi-transparent overlay on the
color raster map, this module gives result with more saturated colors.

The input for this module can be created for example using r.slope.aspect or r.relief .

NULL values are propagated by default, so if any of the two input
rasters contains NULL cell NULL will be also in the output. If -c flag is used and cell in color raster is NULL, just shade color
is used. If cell in shade raster is NULL, shading effect is not
applied and original colors are used. If bgcolor option is used,
NULL value in any input raster will be in the output replaced by the
given color.

---

## See Also

Related tools:
- [`r.his`](https://grass.osgeo.org/grass-devel/manuals/r.his.html)
- [`d.his`](https://grass.osgeo.org/grass-devel/manuals/d.his.html)
- [`d.shade`](https://grass.osgeo.org/grass-devel/manuals/d.shade.html)
- [`g.pnmcomp`](https://grass.osgeo.org/grass-devel/manuals/g.pnmcomp.html)
- [`r.slope.aspect`](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)
- [`r.relief`](https://grass.osgeo.org/grass-devel/manuals/r.relief.html)

---

## Authors

Hamish Bowman Vaclav Petras, NCSU GeoForAll
Lab Inspired by d.shade and manual for r.his .

---

## Resources

- [Official r.shade manual](https://grass.osgeo.org/grass-devel/manuals/r.shade.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.shade.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
