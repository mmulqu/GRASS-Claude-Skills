# r.blend

**Category**: raster

## Description

Blends color components of two raster maps by a given ratio.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_blend(first,second,output,percent=50,nprocs=0,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`first : str | np.ndarray, required`**
   - Name of first raster map for blending
   - Used as: input, raster, name

2. **`second : str | np.ndarray, required`**
   - Name of second raster map for blending
   - Used as: input, raster, name

3. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Basename for red, green and blue output raster maps
   - Used as: output, raster, basename

4. **`percent : float, optional`**
   - Percentage weight of first map for color blending
   - Allowed values: 0-100
   - Default: 50

5. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

6. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Combine resulting R,G,B layers into single output map

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

r.blend blends color components of 2 raster maps by a specified
percentage of the first map.

---

## See Also

Related tools:
- [`d.shade`](https://grass.osgeo.org/grass-devel/manuals/d.shade.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.shade`](https://grass.osgeo.org/grass-devel/manuals/r.shade.html)
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r.his`](https://grass.osgeo.org/grass-devel/manuals/r.his.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.rgb`](https://grass.osgeo.org/grass-devel/manuals/r.rgb.html)
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)

---

## Authors

Unknown: probably CERL Updated to GRASS 5.7 by Michael Barton, Arizona State University

---

## Resources

- [Official r.blend manual](https://grass.osgeo.org/grass-devel/manuals/r.blend.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.blend.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
