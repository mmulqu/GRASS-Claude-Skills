# r.buildvrt

**Category**: raster

## Description

Build a VRT (Virtual Raster) from the list of input raster maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_buildvrt(input=None,file=None,output,title=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], optional`**
   - Name of input raster files
   - Used as: input, raster, name

2. **`file : str | io.StringIO, optional`**
   - Input file with one raster map name per line
   - Used as: input, file, name

3. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

4. **`title : str, optional`**
   - Title for resultant raster map
   - Used as: phrase

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

r.buildvrt builds a virtual raster (VRT) that is a mosaic of the list
of input raster maps. The purpose of such a VRT is to provide fast
access to small subsets of the VRT, also with multiple simultaneous read
requests.

---

## See Also

Related tools:
- [`r.tile`](https://grass.osgeo.org/grass-devel/manuals/r.tile.html)
- [`r.patch`](https://grass.osgeo.org/grass-devel/manuals/r.patch.html)
- [`r.external`](https://grass.osgeo.org/grass-devel/manuals/r.external.html)
- [`r.buildvrt.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.buildvrt.gdal.html)

---

## Resources

- [Official r.buildvrt manual](https://grass.osgeo.org/grass-devel/manuals/r.buildvrt.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.buildvrt.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
