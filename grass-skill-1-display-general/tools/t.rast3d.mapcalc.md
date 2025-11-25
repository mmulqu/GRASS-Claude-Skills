# t.rast3d.mapcalc

**Category**: temporal

## Description

Performs r3.mapcalc expressions on maps of sampled space time 3D raster datasets.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast3d_mapcalc(inputs,expression,method="during,overlap,contain,equal",output,basename,nprocs=1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`inputs : str | list[str], required`**
   - Name of the input space time raster3d datasets
   - Used as: input, str3ds, name

2. **`expression : str, required`**
   - r3.mapcalc expression applied to each time step of the sampled data

3. **`method : str | list[str], optional`**
   - The method to be used for sampling the input dataset
   - Used as: name
   - Allowed values: start, during, overlap, contain, equal, follows, precedes

4. **`output : str, required`**
   - Name of the output space time raster3d dataset
   - Used as: output, str3ds, name

5. **`basename : str, required`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier

6. **`nprocs : int, optional`**
   - Number of r3.mapcalc processes to run in parallel
   - Default: 1

7. **`flags : str, optional`**
   - Allowed values: n, s
   - n
   - Register Null maps
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.mapcalc.html#__tabbed_2_3) for all details)*

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.mapcalc.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast3d.mapcalc provides exact the same functionality as t.rast.mapcalc , but for space time 3D raster datasets. Please refer to t.rast.mapcalc for documentation.

It is a simple wrapper for r3.mapcalc enhanced with
temporal functions.

---

## See Also

Related tools:
- [`t.rast.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/t.rast.mapcalc.html)
- [`t.rast3d.algebra`](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.algebra.html)
- [`r3.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r3.mapcalc.html)

---

## Resources

- [Official t.rast3d.mapcalc manual](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.mapcalc.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.mapcalc.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
