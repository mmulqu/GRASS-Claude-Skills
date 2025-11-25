# r.pack

**Category**: raster

## Description

Exports a raster map as GRASS specific archive file

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_pack(input,output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of raster map to pack up
   - Used as: input, raster, name

2. **`output : str, optional`**
   - Name for output file (default is <input>.pack)
   - Used as: output, file, name

3. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Switch the compression off

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.pack collects raster map elements and support files and compressed
them using gzip algorithm for copying. The resulting packed file can
be afterwards unpacked within a GRASS session by r.unpack . Since the selected raster map is not exported
but natively stored, the current region is not respected. Hence r.pack stores the entire raster map.

---

## See Also

Related tools:
- [`r.unpack`](https://grass.osgeo.org/grass-devel/manuals/r.unpack.html)
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`g.copy`](https://grass.osgeo.org/grass-devel/manuals/g.copy.html)
- [`r.proj`](https://grass.osgeo.org/grass-devel/manuals/r.proj.html)
- [`v.unpack`](https://grass.osgeo.org/grass-devel/manuals/v.unpack.html)

---

## Authors

Original Bash script written by Hamish Bowman, Otago University, New
Zealand Converted to Python and updated for GRASS 7 by Martin Landa, Czech
Technical University in Prague, Czech Republic

---

## Resources

- [Official r.pack manual](https://grass.osgeo.org/grass-devel/manuals/r.pack.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.pack.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
