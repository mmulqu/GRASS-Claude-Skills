# r.in.poly

**Category**: raster

## Description

Creates raster maps from ASCII polygon/line/point data files.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_in_poly(input,output,title=None,type="CELL",null=None,rows=4096,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - Name of input file; or "-" to read from stdin
   - Used as: input, file, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`title : str, optional`**
   - Title for resultant raster map
   - Used as: phrase

4. **`type : str, optional`**
   - Type of raster map to be created
   - Storage type for resultant raster map
   - Allowed values: CELL, FCELL, DCELL
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.in.poly.html#__tabbed_2_3) for all details)*

5. **`null : int, optional`**
   - Integer representing NULL value data cell

6. **`rows : int, optional`**
   - Number of rows to hold in memory
   - Default: 4096

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

r.in.poly allows the creation of GRASS binary raster maps from ASCII
files in the current directory containing polygon, linear, and point
features.

The input file is an ASCII text file containing the polygon, linear,
and point feature definitions. The format of this file is described in
the INPUT FORMAT section below.

The number of raster rows to hold in memory is per default 4096.
This parameter allows users with less memory (or more) on their system
to control how much memory r.in.poly uses. Usually the default value
is fine.

---

## See Also

Related tools:
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`d.rast.edit`](https://grass.osgeo.org/grass-devel/manuals/d.rast.edit.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.in.xyz`](https://grass.osgeo.org/grass-devel/manuals/r.in.xyz.html)
- [`r.patch`](https://grass.osgeo.org/grass-devel/manuals/r.patch.html)
- [`v.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html)

---

## Resources

- [Official r.in.poly manual](https://grass.osgeo.org/grass-devel/manuals/r.in.poly.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.poly.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
