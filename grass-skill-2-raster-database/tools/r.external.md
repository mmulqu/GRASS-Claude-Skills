# r.external

**Category**: raster

## Description

Links GDAL supported raster data as a pseudo GRASS raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_external(input=None,source=None,output,band=None,title=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, optional`**
   - Name of raster file to be linked
   - Used as: input, file, name

2. **`source : str, optional`**
   - Name of non-file GDAL data source
   - Used as: name

3. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

4. **`band : int, optional`**
   - Band to select (default is all bands)

5. **`title : str, optional`**
   - Title for resultant raster map
   - Used as: phrase

6. **`flags : str, optional`**
   - Allowed values: f, o, j, e, a, h, v, t, m, r
   - f
   - List supported formats and exit
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.external.html#__tabbed_2_3) for all details)*

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

r.external allows a user to link a GDAL supported raster file to a
binary raster map layer, from any GDAL supported raster map format, with
an optional title. The file is not imported but just registered as GRASS
raster map.

---

## See Also

Related tools:
- [`r.import`](https://grass.osgeo.org/grass-devel/manuals/r.import.html)
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`r.external.out`](https://grass.osgeo.org/grass-devel/manuals/r.external.out.html)

---

## Resources

- [Official r.external manual](https://grass.osgeo.org/grass-devel/manuals/r.external.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.external.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
