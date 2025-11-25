# v.in.e00

**Category**: vector

## Description

Imports E00 file into a vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_in_e00(input,type="point",output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input E00 file
   - Used as: input, file, name

2. **`type : str | list[str], required`**
   - Input feature type
   - Allowed values: point, line, area
   - Default: point

3. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

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

v.in.e00 imports ASCII and binary E00 vector maps into GRASS.

---

## See Also

Related tools:
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)

---

## Authors

Markus Neteler, Otto Dassau, GDF Hannover
bR , Germany

---

## Resources

- [Official v.in.e00 manual](https://grass.osgeo.org/grass-devel/manuals/v.in.e00.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.in.e00.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
