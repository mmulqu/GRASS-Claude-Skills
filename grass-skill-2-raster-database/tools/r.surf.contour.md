# r.surf.contour

**Category**: raster

## Description

Generates surface raster map from rasterized contours.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_surf_contour(input,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map containing contours
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.surf.contour creates a raster elevation map from a rasterized
contour map. Elevation values are determined using procedures similar to
a manual methods. To determine the elevation of a point on a contour
map, an individual might interpolate its value from those of the two
nearest contour lines (uphill and downhill).

r.surf.contour works in a similar way. Initially, a vector map of the
contour lines is made with the elevation of each line as an attribute.
When the program v.to.rast is run on the vector map,
continuous "lines" of rasters containing the contour line values will be
the input for r.surf.contour . For each cell in the input map, either
the cell is a contour line cell (which is given that value), or a flood
fill is generated from that spot until the fill comes to two unique
values. So the r.surf.contour algorithm linearly interpolates between contour lines. The flood fill is not allowed to cross over the
rasterized contour lines, thus ensuring that an uphill and downhill
contour value will be the two values chosen. r.surf.contour interpolates from the uphill and downhill values by the true distance.

input = name Name of an existing raster map that contains a set of initial category
values (i.e., some cells contain known elevation values (denoting
contours) while the rest contain NULL values).

output = name Name to be assigned to new output raster map that represents a smooth
(e.g., elevation) surface generated from the known category values in
the input raster map layer.

An existing mask raster map is respected for both reading input and
writing output .

---

## See Also

Related tools:
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.slope.aspect`](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)
- [`r.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/r.surf.idw.html)
- [`v.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/v.surf.idw.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)
- [`v.to.rast`](https://grass.osgeo.org/grass-devel/manuals/v.to.rast.html)

---

## Resources

- [Official r.surf.contour manual](https://grass.osgeo.org/grass-devel/manuals/r.surf.contour.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.surf.contour.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
