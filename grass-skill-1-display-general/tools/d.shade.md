# d.shade

**Category**: display

## Description

Drapes a color raster over an shaded relief or aspect map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_shade(shade,color,brighten=0,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`shade : str | np.ndarray, required`**
   - Name of shaded relief or aspect raster map
   - Used as: input, raster, name

2. **`color : str | np.ndarray, required`**
   - Name of raster to drape over relief raster map
   - Typically, this raster is elevation or other colorful raster
   - Used as: input, raster, name

3. **`brighten : int, optional`**
   - Percent to brighten
   - Allowed values: -99-99
   - Default: 0

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

d.shade will drape a color raster map over a shaded relief map. In
place of shaded relief, any raster map can be used including aspect or
slope. The color raster map is usually an elevation raster map with
colorful color table (as opposed to gray scale color table). However,
any raster map can be used including categorical raster maps.

The advantage of this module is that it allows visualizing the shaded
map without a need to create a new raster which would combine both.
Comparing to creating shaded relief as semi-transparent overlay on the
color raster map, this module gives result with more saturated colors.

The input for this module can be created for example using r.slope.aspect or r.relief .

---

## See Also

Related tools:
- [`d.his`](https://grass.osgeo.org/grass-devel/manuals/d.his.html)
- [`g.pnmcomp`](https://grass.osgeo.org/grass-devel/manuals/g.pnmcomp.html)
- [`r.shade`](https://grass.osgeo.org/grass-devel/manuals/r.shade.html)
- [`r.slope.aspect`](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)
- [`r.relief`](https://grass.osgeo.org/grass-devel/manuals/r.relief.html)

---

## Authors

Unknown; updated to GRASS 5.7 by Michael Barton

---

## Resources

- [Official d.shade manual](https://grass.osgeo.org/grass-devel/manuals/d.shade.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.shade.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
