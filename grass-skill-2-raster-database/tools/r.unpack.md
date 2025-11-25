# r.unpack

**Category**: raster

## Description

Imports a GRASS specific raster archive file (packed with r.pack) as a raster map

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_unpack(input,output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input pack file
   - Used as: input, file, name.pack

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map (default: taken from input file internals)
   - Used as: output, raster, name

3. **`flags : str, optional`**
   - Allowed values: o, p
   - o
   - Override projection check (use current projects's CRS)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.unpack.html#__tabbed_2_3) for all details)*

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

r.unpack allows unpacking raster maps packed by r.pack .

---

## See Also

Related tools:
- [`r.pack`](https://grass.osgeo.org/grass-devel/manuals/r.pack.html)
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`v.pack`](https://grass.osgeo.org/grass-devel/manuals/v.pack.html)

---

## Authors

Original Bash script written by Hamish Bowman, Otago University, New
Zealand as GRASS AddOns Converted to Python and updated for GRASS 7 by Martin Landa, CTU in
Prague, Czech Republic

---

## Resources

- [Official r.unpack manual](https://grass.osgeo.org/grass-devel/manuals/r.unpack.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.unpack.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
