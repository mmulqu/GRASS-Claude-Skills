# r.resamp.interp

**Category**: raster

## Description

Resamples raster map to a finer grid using interpolation.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_resamp_interp(input,output,method="bilinear",nprocs=0,memory=300,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`method : str, optional`**
   - Sampling interpolation method
   - Allowed values: nearest, bilinear, bicubic, lanczos
   - nearest: Nearest-neighbor interpolation
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.resamp.interp.html#__tabbed_2_3) for all details)*

4. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

5. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.resamp.interp resamples an input raster map by interpolating between
the neighboring cells via a selectable resampling algorithm. All cells
present in the neighborhood of the input raster cell must be non-null to
generate a non-null cell in the output raster map. A choice of four
interpolation methods is available; each uses the weighted values of a
different number of adjacent cells in the input map to determine the
value of each cell in the output map as follows:

This module is intended for reinterpolation of continuous data to a
different resolution rather than for interpolation from scattered data
(use the v.surf.* modules for that purpose).

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.resample`](https://grass.osgeo.org/grass-devel/manuals/r.resample.html)
- [`r.resamp.filter`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.filter.html)
- [`r.resamp.rst`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.rst.html)
- [`r.resamp.stats`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.stats.html)

---

## Resources

- [Official r.resamp.interp manual](https://grass.osgeo.org/grass-devel/manuals/r.resamp.interp.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.resamp.interp.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
