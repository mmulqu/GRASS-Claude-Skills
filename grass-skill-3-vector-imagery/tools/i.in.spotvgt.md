# i.in.spotvgt

**Category**: imagery

## Description

Imports SPOT VGT NDVI data into a raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_in_spotvgt(input,output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - Name of input SPOT VGT NDVI HDF file
   - Used as: input, file, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`flags : str, optional`**
   - Allowed values: a
   - a
   - Also import quality map (SM status map layer) and filter NDVI map

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

i.in.spotvgt imports SPOT Vegetation (1km, global) NDVI data sets.
After import the digital numbers (DN) are remapped to VEGETATION NDVI
values and the NDVI color table is applied. The imported DN map is
removed after remapping.

Apparently missing raster cells due to bad pixel quality are
reconstructed by the SPOT operating team in the NDVI file. The
differences between the filtered (-a flag) and raw NDVI map should be
compared.

---

## See Also

Related tools:
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`r.out.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.out.gdal.html)

---

## Resources

- [Official i.in.spotvgt manual](https://grass.osgeo.org/grass-devel/manuals/i.in.spotvgt.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.in.spotvgt.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
