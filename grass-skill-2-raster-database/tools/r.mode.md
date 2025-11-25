# r.mode

**Category**: raster

## Description

Finds the mode of values in a cover map within areas assigned the same category value in a user-specified base map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_mode(base,cover,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`base : str | np.ndarray, required`**
   - Base map to be reclassified
   - Used as: input, raster

2. **`cover : str | np.ndarray, required`**
   - Coverage map
   - Used as: input, raster

3. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Output map
   - Used as: output, raster

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

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.mode calculates the most frequently occurring value (i. e., mode) of
data contained in a cover raster map layer for areas assigned the same
category value in the user-specified base raster map layer. These
modes are stored in the new output map layer.

The output map is actually a reclass of the base map.

The base parameter defines an existing raster map layer in the
user's current mapset search path. For each group of cells assigned the
same category value in the base map, the mode of the values assigned
these cells in the cover map will be computed.

The cover parameter defines an existing raster map layer containing
the values to be used to compute the mode within each category of the base map.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.category`](https://grass.osgeo.org/grass-devel/manuals/r.category.html)
- [`r.clump`](https://grass.osgeo.org/grass-devel/manuals/r.clump.html)
- [`r.describe`](https://grass.osgeo.org/grass-devel/manuals/r.describe.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.mfilter`](https://grass.osgeo.org/grass-devel/manuals/r.mfilter.html)
- [`r.neighbors`](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)
- [`r.reclass`](https://grass.osgeo.org/grass-devel/manuals/r.reclass.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)
- [`r.statistics`](https://grass.osgeo.org/grass-devel/manuals/r.statistics.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)

---

## Resources

- [Official r.mode manual](https://grass.osgeo.org/grass-devel/manuals/r.mode.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.mode.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
