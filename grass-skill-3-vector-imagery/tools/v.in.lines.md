# v.in.lines

**Category**: vector

## Description

Imports ASCII x,y[,z] coordinates as a series of lines.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_in_lines(input,output,separator="pipe",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - Name of input file (or "-" to read from stdin)
   - Used as: input, file, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

4. **`flags : str, optional`**
   - Allowed values: z
   - z
   - Create a 3D line from 3 column data

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

Imports a stream of ASCII x,y[,z] coordinates as a line or series of
lines.

---

## See Also

Related tools:
- [`d.graph`](https://grass.osgeo.org/grass-devel/manuals/d.graph.html)
- [`v.centroids`](https://grass.osgeo.org/grass-devel/manuals/v.centroids.html)
- [`v.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html)
- [`v.in.mapgen`](https://grass.osgeo.org/grass-devel/manuals/v.in.mapgen.html)
- [`v.in.region`](https://grass.osgeo.org/grass-devel/manuals/v.in.region.html)
- [`v.out.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.out.ascii.html)
- [`r.in.poly`](https://grass.osgeo.org/grass-devel/manuals/r.in.poly.html)

---

## Resources

- [Official v.in.lines manual](https://grass.osgeo.org/grass-devel/manuals/v.in.lines.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.in.lines.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
