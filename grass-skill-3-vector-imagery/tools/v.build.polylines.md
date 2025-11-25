# v.build.polylines

**Category**: vector

## Description

Builds polylines from lines or boundaries.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_build_polylines(input,output,cats="no",type="line,boundary",overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`cats : str, optional`**
   - Category number mode
   - Allowed values: no, first, multi, same
   - no: Do not assign any category number to polyline
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.build.polylines.html#__tabbed_2_3) for all details)*

4. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: line, boundary
   - Default: line,boundary

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

v.build.polylines builds polylines from the lines or boundaries in a
vector map.

A line is defined by one start node, one end node and any number of
vertices between the start and end nodes. The shortest possible line
consists of only two vertices where the coordinates of the start and end
nodes are identical to those of the two vertices.

v.build.polylines picks a line and from its start node, walks back as
long as exactly one other line of the same type is connected to this
node. Line directions are reversed as required, i.e. it does not matter
if the next line is connected to the current node by its start or end
node. Once the start line of a polyline is identified, it walks forward
and adds all vertices (in reverse order if needed) of connected lines to
the start line, i.e. the start line and connecting lines are reversed as
needed. That is, if a line is reversed depends on what node is initially
picked for building polylines. If the direction of lines is important
(it's not for boundaries to build areas), you have to manually change
line directions with either v.edit or the wxGUI vector
digitizer .

Polylines provide the most appropriate representation of curved lines
when it is important that nodes serve to define topology rather than
geometry. Curved lines are usually digitized as polylines, but these are
sometimes broken into their constituent straight line segments during
conversion from one data format to another. v.build.polylines can be
used to rebuild such broken polylines.

---

## See Also

Related tools:
- [`v.build`](https://grass.osgeo.org/grass-devel/manuals/v.build.html)
- [`v.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html)
- [`v.edit`](https://grass.osgeo.org/grass-devel/manuals/v.edit.html)
- [`v.split`](https://grass.osgeo.org/grass-devel/manuals/v.split.html)

---

## Authors

Mark Lake, Institute of Archaeology, University College London. Major rewrite by Radim Blazek, October 2002 Category mode added by Martin Landa, FBK-irst, Trento, Italy, October
2007 Support for categories, attributes, and different line types by Markus
Metz

---

## Resources

- [Official v.build.polylines manual](https://grass.osgeo.org/grass-devel/manuals/v.build.polylines.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.build.polylines.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
