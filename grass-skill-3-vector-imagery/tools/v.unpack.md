# v.unpack

**Category**: vector

## Description

Imports a GRASS specific vector archive file (packed with v.pack) as a vector map

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_unpack(input,output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input pack file
   - Used as: input, file, name.pack

2. **`output : str, optional`**
   - Name for output vector map
   - Default: taken from input file internals
   - Used as: output, vector, name

3. **`flags : str, optional`**
   - Allowed values: o, p
   - o
   - Override projection check (use current projects's CRS)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.unpack.html#__tabbed_2_3) for all details)*

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

v.unpack allows unpacking vector maps packed by v.pack .

---

## See Also

Related tools:
- [`v.pack`](https://grass.osgeo.org/grass-devel/manuals/v.pack.html)
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)
- [`r.pack`](https://grass.osgeo.org/grass-devel/manuals/r.pack.html)

---

## Resources

- [Official v.unpack manual](https://grass.osgeo.org/grass-devel/manuals/v.unpack.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.unpack.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
