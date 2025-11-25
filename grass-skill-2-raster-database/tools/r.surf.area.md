# r.surf.area

**Category**: raster

## Description

Prints estimation of surface area for raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_surf_area(map,vscale=1.0,units=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map
   - Used as: input, raster, name

2. **`vscale : float, optional`**
   - Vertical scale
   - Default: 1.0

3. **`units : str, optional`**
   - Output units
   - Default: square map units
   - Allowed values: miles, feet, meters, kilometers, acres, hectares

4. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

5. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

6. **`superquiet : bool, optional`**
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

r.surf.area calculates area of regular 3D triangulated points (centers
of cells) in current region by adding areas of triangles. Therefore,
area of a flat surface will be reported as
( rows + cols -1) * (area of cell) less than area of flat region due to
a half row and half column missing around the perimeter.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/r.surf.idw.html)
- [`r.surf.fractal`](https://grass.osgeo.org/grass-devel/manuals/r.surf.fractal.html)
- [`r.surf.gauss`](https://grass.osgeo.org/grass-devel/manuals/r.surf.gauss.html)
- [`r.volume`](https://grass.osgeo.org/grass-devel/manuals/r.volume.html)
- [`r.slope.aspect`](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)
- [`v.to.rast`](https://grass.osgeo.org/grass-devel/manuals/v.to.rast.html)

---

## Resources

- [Official r.surf.area manual](https://grass.osgeo.org/grass-devel/manuals/r.surf.area.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.surf.area.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
