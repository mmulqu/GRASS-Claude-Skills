# r.reclass.area

**Category**: raster

## Description

Reclasses a raster map greater or less than user specified area size (in hectares).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_reclass_area(input,output,value,mode,method="reclass",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`value : float, required`**
   - Value option that sets the area size limit (in hectares)

4. **`mode : str, required`**
   - Lesser or greater than specified value
   - Allowed values: lesser, greater

5. **`method : str, optional`**
   - Method used for reclassification
   - Allowed values: reclass, rmarea
   - Default: reclass

6. **`flags : str, optional`**
   - Allowed values: c, d
   - c
   - Input map is clumped
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.reclass.area.html#__tabbed_2_3) for all details)*

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

r.reclass.area reclasses a raster map greater or less than a user
specified area size (in hectares).

If the -c flag is used, r.reclass.area will skip the creation of a
clumped raster and assume that the input raster is already clumped.

---

## See Also

Related tools:
- [`r.reclass`](https://grass.osgeo.org/grass-devel/manuals/r.reclass.html)
- [`r.clump`](https://grass.osgeo.org/grass-devel/manuals/r.clump.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)

---

## Authors

NRCS, Markus Neteler

---

## Resources

- [Official r.reclass.area manual](https://grass.osgeo.org/grass-devel/manuals/r.reclass.area.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.reclass.area.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
