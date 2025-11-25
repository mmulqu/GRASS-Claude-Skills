# v.in.mapgen

**Category**: vector

## Description

Imports Mapgen or Matlab-ASCII vector maps into GRASS.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_in_mapgen(input,output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - Name of input file in Mapgen/Matlab format
   - Used as: input, file, name

2. **`output : str, optional`**
   - Name for output vector map (omit for display to stdout)
   - Used as: output, vector, name

3. **`flags : str, optional`**
   - Allowed values: f, z
   - f
   - Input map is in Matlab format
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.in.mapgen.html#__tabbed_2_3) for all details)*

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

v.in.mapgen allows the user to import Mapgen or Matlab vector maps
into GRASS.

---

## See Also

Related tools:
- [`v.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html)

---

## Authors

Based on v.in.mapgen.sh for GRASS 5.0 by Andreas Lange Rewritten for GRASS 6 by Hamish Bowman

---

## Resources

- [Official v.in.mapgen manual](https://grass.osgeo.org/grass-devel/manuals/v.in.mapgen.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.in.mapgen.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
