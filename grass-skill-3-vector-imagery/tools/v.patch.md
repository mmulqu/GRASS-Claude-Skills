# v.patch

**Category**: vector

## Description

Creates a new vector map by combining other vector maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_patch(input,output,bbox=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - Name of input vector map(s)
   - Or data source(s) for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`bbox : str, optional`**
   - Name for output vector map where bounding boxes of input vector maps are written to
   - Used as: output, vector, name

4. **`flags : str, optional`**
   - Allowed values: n, z, e, a, b
   - n
   - Do not expect input with topology
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.patch.html#__tabbed_2_3) for all details)*

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.patch allows the user to combine any number of vector maps together
to create one composite vector map. If the table structures are
identical, attributes are transferred to the new table.

---

## See Also

Related tools:
- [`v.clean`](https://grass.osgeo.org/grass-devel/manuals/v.clean.html)
- [`v.build`](https://grass.osgeo.org/grass-devel/manuals/v.build.html)
- [`v.select`](https://grass.osgeo.org/grass-devel/manuals/v.select.html)
- [`v.overlay`](https://grass.osgeo.org/grass-devel/manuals/v.overlay.html)

---

## Authors

Dave Gerdes, U.S.Army Construction Engineering Research Laboratory Radim Blazek, ITC-Irst, Trento, Italy

---

## Resources

- [Official v.patch manual](https://grass.osgeo.org/grass-devel/manuals/v.patch.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.patch.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
