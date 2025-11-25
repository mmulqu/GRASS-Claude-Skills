# v.segment

**Category**: vector

## Description

Creates points/segments from input vector lines and positions.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_segment(input,layer="1",output,rules=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector lines map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

4. **`rules : str | io.StringIO, optional`**
   - Name of file containing segment rules
   - '-' for standard input
   - Used as: input, file, name

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

v.segment generates segments or points from input lines and from
positions read from a text file or ' stdin '. It includes the creation
of parallel lines or points in given destination from the line.

The format is:

The offsets can be percent values of the line length. If the offsets are
negative, they start from the end node of the line. -0 means the end of
the line.

The user could send to stdin something like:

(pipe or redirect from file into the command).

---

## See Also

Related tools:
- [`d.vect`](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)
- [`v.build.polylines`](https://grass.osgeo.org/grass-devel/manuals/v.build.polylines.html)
- [`v.lrs.segment`](https://grass.osgeo.org/grass-devel/manuals/v.lrs.segment.html)
- [`v.parallel`](https://grass.osgeo.org/grass-devel/manuals/v.parallel.html)
- [`v.split`](https://grass.osgeo.org/grass-devel/manuals/v.split.html)
- [`v.to.db`](https://grass.osgeo.org/grass-devel/manuals/v.to.db.html)
- [`v.to.points`](https://grass.osgeo.org/grass-devel/manuals/v.to.points.html)

---

## Resources

- [Official v.segment manual](https://grass.osgeo.org/grass-devel/manuals/v.segment.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.segment.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
