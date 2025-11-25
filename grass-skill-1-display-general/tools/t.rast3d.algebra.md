# t.rast3d.algebra

**Category**: temporal

## Description

Apply temporal and spatial operations on space time 3D raster datasets using temporal 3D raster algebra.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast3d_algebra(expression,basename,nprocs=1,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`expression : str, required`**
   - Algebraic expression for temporal and spatial analysis of space time 3D raster datasets

2. **`basename : str, required`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier

3. **`nprocs : int, optional`**
   - Number of r3.mapcalc processes to run in parallel
   - Default: 1

4. **`flags : str, optional`**
   - Allowed values: s, n, g
   - s
   - Check the spatial topology of temporally related maps and process only spatially related maps
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.algebra.html#__tabbed_2_3) for all details)*

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast3d.algebra performs temporal and spatial map algebra operations
on space time 3D raster datasets (STR3DS) by using the temporal 3D
raster algebra.

The module expects an expression as input parameter in the following
form:

"result = expression"

The statement structure is exact the same as of t.rast.algebra , see t.rast.algebra but allows four-dimensional
indexing.

---

## See Also

Related tools:
- [`t.rast.algebra`](https://grass.osgeo.org/grass-devel/manuals/t.rast.algebra.html)
- [`t.rast3d.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.mapcalc.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`t.vect.algebra`](https://grass.osgeo.org/grass-devel/manuals/t.vect.algebra.html)
- [`t.select`](https://grass.osgeo.org/grass-devel/manuals/t.select.html)

---

## Authors

Thomas Leppelt, Sören Gebbert, Thünen Institute of Climate-Smart
Agriculture

---

## Resources

- [Official t.rast3d.algebra manual](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.algebra.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.algebra.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
