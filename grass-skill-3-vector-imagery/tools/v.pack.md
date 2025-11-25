# v.pack

**Category**: vector

## Description

Exports a vector map as GRASS specific archive file

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_pack(input,output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of vector map to pack up
   - Used as: input, vector, name

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

v.pack collects (packs) vector map elements and support files in GRASS
Database and creates an compressed file using gzip algorithm. This
file can be used to copy the vector map to another machine. The packed
file can be afterwards unpacked by v.unpack .

---

## See Also

Related tools:
- [`v.unpack`](https://grass.osgeo.org/grass-devel/manuals/v.unpack.html)
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)
- [`g.copy`](https://grass.osgeo.org/grass-devel/manuals/g.copy.html)
- [`v.proj`](https://grass.osgeo.org/grass-devel/manuals/v.proj.html)
- [`r.unpack`](https://grass.osgeo.org/grass-devel/manuals/r.unpack.html)

---

## Resources

- [Official v.pack manual](https://grass.osgeo.org/grass-devel/manuals/v.pack.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.pack.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
