# r.reclass

**Category**: raster

## Description

Reclassify raster map based on category values. Creates a new raster map whose category values are based upon a reclassification of the categories in an existing raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_reclass(input,output,rules,title=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of raster map to be reclassified
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`rules : str | io.StringIO, required`**
   - File containing reclass rules
   - '-' for standard input
   - Used as: input, file, name

4. **`title : str, optional`**
   - Title for output raster map

5. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
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

r.reclass creates an output map layer based on an input integer
raster map layer. The output map layer will be a reclassification of the
input map layer based on reclass rules input to r.reclass , and can be
treated in much the same way that raster maps are treated. A TITLE for
the output map layer may be (optionally) specified by the user.

The reclass rules are read from standard input (i.e., from the keyboard,
redirected from a file, or piped through another program).

Before using r.reclass the user must know the following:

---

## See Also

Related tools:
- [`r.recode`](https://grass.osgeo.org/grass-devel/manuals/r.recode.html)
- [`r.resample`](https://grass.osgeo.org/grass-devel/manuals/r.resample.html)
- [`r.rescale`](https://grass.osgeo.org/grass-devel/manuals/r.rescale.html)

---

## Authors

James Westervelt, Michael Shapiro U.S.Army Construction Engineering Research Laboratory

---

## Resources

- [Official r.reclass manual](https://grass.osgeo.org/grass-devel/manuals/r.reclass.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.reclass.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
