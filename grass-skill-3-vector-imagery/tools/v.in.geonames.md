# v.in.geonames

**Category**: vector

## Description

Imports geonames.org country files into a vector points map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_in_geonames(input,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - Name of uncompressed geonames file (with .txt extension)
   - Used as: input, file, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

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

v.in.geonames imports Geonames.org country files (Gazetteer data) into
a GRASS vector points map. The country files can be downloaded from the GeoNames Data Dump Server .
Only original files can be processed (unzip compressed file first).
These Geonames files are encoded in UTF-8 which is maintained in the
GRASS database.

---

## See Also

Related tools:
- [`db.connect`](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [`v.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html)
- [`v.select`](https://grass.osgeo.org/grass-devel/manuals/v.select.html)

---

## Resources

- [Official v.in.geonames manual](https://grass.osgeo.org/grass-devel/manuals/v.in.geonames.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.in.geonames.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
