# r.cross

**Category**: raster

## Description

Creates a cross product of the category values from multiple raster map layers.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_cross(input,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - Names of 2-30 input raster maps
   - Used as: input, raster

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`flags : str, optional`**
   - Allowed values: z
   - z
   - Non-NULL data only

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

r.cross creates an output raster map layer representing all unique
combinations of category values in the raster input layers
( input = name,name,name , ...). At least two, but not more than 30, input map layers must be specified. The user must also specify a name
to be assigned to the output raster map layer created by r.cross .

---

## See Also

Related tools:
- [`r.covar`](https://grass.osgeo.org/grass-devel/manuals/r.covar.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)

---

## Resources

- [Official r.cross manual](https://grass.osgeo.org/grass-devel/manuals/r.cross.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.cross.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
