# v.out.dxf

**Category**: vector

## Description

Exports vector map to DXF file format.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_out_dxf(input,layer="-1",output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name ('-1' for all layers)
   - A single vector map can be connected to multiple database tables. This number determines which table to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`output : str, required`**
   - Name for DXF output file
   - Used as: output, file, name

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

The GRASS program v.out.dxf conversion program generates an ASCII DXF
(AutoCAD) file from a GRASS vector. The output file is placed in the
user's current working directory unless the user specifies a full
pathname for the output .

---

## See Also

Related tools:
- [`v.in.dxf`](https://grass.osgeo.org/grass-devel/manuals/v.in.dxf.html)

---

## Authors

Charles Ehlschlaeger, U.S. Army Construction Engineering Research
Laboratory, wrote original v.out.dxf program in 4/89.
Update to GRASS 5.7 Radim Blazek, 10/2004

---

## Resources

- [Official v.out.dxf manual](https://grass.osgeo.org/grass-devel/manuals/v.out.dxf.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.out.dxf.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
