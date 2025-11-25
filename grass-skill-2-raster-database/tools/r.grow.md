# r.grow

**Category**: raster

## Description

Generates a raster map layer with contiguous areas grown by one cell.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_grow(input,output,radius=1.01,metric="euclidean",old=None,new=None,nprocs=0,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`radius : float, optional`**
   - Radius of buffer in raster cells
   - Default: 1.01

4. **`metric : str, optional`**
   - Metric
   - Allowed values: euclidean, maximum, manhattan
   - Default: euclidean

5. **`old : int, optional`**
   - Value to write for input cells which are non-NULL (-1 => NULL)

6. **`new : int, optional`**
   - Value to write for "grown" cells

7. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

8. **`flags : str, optional`**
   - Allowed values: m
   - m
   - Radius is in map units rather than cells

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


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.grow.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.grow adds cells around the perimeters of all areas in a
user-specified raster map layer and stores the output in a new raster
map layer. The user can use it to grow by one or more than one cell (by
varying the size of the radius parameter), or like r.buffer , but
with the option of preserving the original cells (similar to combining r.buffer and r.patch ).

If radius is negative, r.grow shrinks areas by removing cells
around the perimeters of all areas.

---

## See Also

Related tools:
- [`r.buffer`](https://grass.osgeo.org/grass-devel/manuals/r.buffer.html)
- [`r.grow.distance`](https://grass.osgeo.org/grass-devel/manuals/r.grow.distance.html)
- [`r.patch`](https://grass.osgeo.org/grass-devel/manuals/r.patch.html)

---

## Authors

Marjorie Larson, U.S. Army Construction Engineering Research Laboratory
Glynn Clements

---

## Resources

- [Official r.grow manual](https://grass.osgeo.org/grass-devel/manuals/r.grow.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.grow.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
