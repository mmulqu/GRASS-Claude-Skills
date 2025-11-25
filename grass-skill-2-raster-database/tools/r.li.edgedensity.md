# r.li.edgedensity

**Category**: raster

## Description

Calculates edge density index on a raster map, using a 4 neighbour algorithm

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_li_edgedensity(input,config,output,patch_type=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`config : str | io.StringIO, required`**
   - Configuration file
   - Used as: input, file, name

3. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

4. **`patch_type : str, optional`**
   - The value of the patch type
   - It can be integer, double or float; it will be changed in function of map type

5. **`flags : str, optional`**
   - Allowed values: b
   - b
   - Exclude border edges

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

r.li.edgedensity calculates:

with:

The unit is meters per hectare.

---

## See Also

Related tools:
- [`r.li`](https://grass.osgeo.org/grass-devel/manuals/r.li.html)
- [`g.gui.rlisetup`](https://grass.osgeo.org/grass-devel/manuals/g.gui.rlisetup.html)

---

## Authors

Serena Pallecchi, student of Computer Science University of Pisa
(Italy). Commission from Faunalia Pontedera (PI), Italy ( ) Markus Metz

---

## Resources

- [Official r.li.edgedensity manual](https://grass.osgeo.org/grass-devel/manuals/r.li.edgedensity.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.li.edgedensity.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
