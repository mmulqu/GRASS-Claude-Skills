# r.relief

**Category**: raster

## Description

Creates shaded relief map from an elevation map (DEM).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_relief(input,output,altitude=30,azimuth=270,zscale=1,scale=1,units=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster (typically elevation) map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output shaded relief map
   - Used as: output, raster, name

3. **`altitude : float, optional`**
   - Altitude of the sun in degrees above the horizon
   - Allowed values: 0-90
   - Default: 30

4. **`azimuth : float, optional`**
   - Azimuth of the sun in degrees to the east of north
   - Allowed values: 0-360
   - Default: 270

5. **`zscale : float, optional`**
   - Factor for exaggerating relief
   - Default: 1

6. **`scale : float, optional`**
   - Scale factor for converting meters to elevation units
   - Default: 1

7. **`units : str, optional`**
   - Elevation units (overrides scale factor)
   - Allowed values: intl, survey

8. **`intl: international feet`**
   - survey: survey feet

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


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.relief.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.relief creates a raster shaded relief map based on current
resolution settings and on sun altitude, azimuth, and z-exaggeration
values entered by the user.

The parameters controlling the shading are:

r.relief assigns a grey-scale color table to the new shaded relief
map.

---

## See Also

Related tools:
- [`d.shade`](https://grass.osgeo.org/grass-devel/manuals/d.shade.html)
- [`d.his`](https://grass.osgeo.org/grass-devel/manuals/d.his.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.shade`](https://grass.osgeo.org/grass-devel/manuals/r.shade.html)
- [`r.blend`](https://grass.osgeo.org/grass-devel/manuals/r.blend.html)
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.resamp.interp`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.interp.html)

---

## Authors

Jim Westervelt, U.S. Army Construction Engineering Research Laboratory Markus Metz: Enhanced fast C version of r.relief for GRASS GIS 7

---

## Resources

- [Official r.relief manual](https://grass.osgeo.org/grass-devel/manuals/r.relief.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.relief.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
