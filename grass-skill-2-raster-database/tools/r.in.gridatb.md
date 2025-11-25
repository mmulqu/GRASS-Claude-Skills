# r.in.gridatb

**Category**: raster

## Description

Imports GRIDATB.FOR map file (TOPMODEL) into a GRASS raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_in_gridatb(input,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - GRIDATB i/o map file
   - Used as: input, file, name

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

r.in.gridatb imports GRIDATB.FOR map file (TOPMODEL) into GRASS raster
map.

---

## See Also

Related tools:
- [`r.topmodel`](https://grass.osgeo.org/grass-devel/manuals/r.topmodel.html)
- [`r.out.gridatb`](https://grass.osgeo.org/grass-devel/manuals/r.out.gridatb.html)

---

## Resources

- [Official r.in.gridatb manual](https://grass.osgeo.org/grass-devel/manuals/r.in.gridatb.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.gridatb.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
