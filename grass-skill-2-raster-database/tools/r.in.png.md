# r.in.png

**Category**: raster

## Description

Imports non-georeferenced PNG format image.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_in_png(input,output,title=None,gamma=None,alpha=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input file
   - Used as: input, file, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`title : str, optional`**
   - Title for created raster map

4. **`gamma : float, optional`**
   - Display gamma

5. **`alpha : float, optional`**
   - Alpha threshold

6. **`flags : str, optional`**
   - Allowed values: f, h
   - f
   - Create floating-point map (0.0 - 1.0)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.in.png.html#__tabbed_2_3) for all details)*

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

r.in.png imports a non-georeferenced Portable Network Graphics (PNG)
image as a GRASS raster map. Georeferencing .wld files are not
supported, for that r.import can be used.

---

## See Also

Related tools:
- [`r.import`](https://grass.osgeo.org/grass-devel/manuals/r.import.html)
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`r.out.png`](https://grass.osgeo.org/grass-devel/manuals/r.out.png.html)
- [`r.region`](https://grass.osgeo.org/grass-devel/manuals/r.region.html)

---

## Authors

Michael Shapiro Alex Shevlakov Glynn Clements

---

## Resources

- [Official r.in.png manual](https://grass.osgeo.org/grass-devel/manuals/r.in.png.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.png.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
