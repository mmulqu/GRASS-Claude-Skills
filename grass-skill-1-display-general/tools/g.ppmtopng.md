# g.ppmtopng

**Category**: general

## Description

Converts between PPM/PGM and PNG image formats.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_ppmtopng(input,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - Name of input file
   - Used as: input, file, name

2. **`output : str, required`**
   - Name for output file
   - Used as: output, file, name

3. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

4. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

5. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

6. **`superquiet : bool, optional`**
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

g.ppmtopng isn't meant for end users. It's a utility to convert
between PPM/PGM and PNG image formats.

---

## Resources

- [Official g.ppmtopng manual](https://grass.osgeo.org/grass-devel/manuals/g.ppmtopng.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.ppmtopng.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
