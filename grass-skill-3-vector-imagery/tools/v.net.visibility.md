# v.net.visibility

**Category**: vector

## Description

Performs visibility graph construction.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_net_visibility(input,output,coordinates=None,visibility=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`coordinates : tuple[float, float] | list[float] | str, optional`**
   - Coordinates
   - Used as: input, coords, east,north

4. **`visibility : str, optional`**
   - Name of input vector map containing visible points
   - Add points after computing the visibility graph
   - Used as: input, vector, name

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

v.net.visibility computes the visibility graph of a vector map
containing lines, areas (boundaries) and points. The visibility graph is
the graph where the nodes are the end point of the lines, boundaries or
simply points. There is an edge between two nodes if they are 'visible'
to each other. Two nodes are visibible if there are no segments in
between of them, i.e. the edge does not intersect any line or boundary
in the vector map. This is useful to compute the shortest path in a
vector map from any two points. To do this, first you need to compute
the visibility graph and from that to compute the shortest path using v.net.path or d.path .

IMPORTANT: the algorithm doesn't work well with intersecting lines
(that includes overlapping)

---

## See Also

Related tools:
- [`d.path`](https://grass.osgeo.org/grass-devel/manuals/d.path.html)
- [`v.net`](https://grass.osgeo.org/grass-devel/manuals/v.net.html)
- [`v.net.alloc`](https://grass.osgeo.org/grass-devel/manuals/v.net.alloc.html)
- [`v.net.iso`](https://grass.osgeo.org/grass-devel/manuals/v.net.iso.html)
- [`v.net.salesman`](https://grass.osgeo.org/grass-devel/manuals/v.net.salesman.html)
- [`v.net.steiner`](https://grass.osgeo.org/grass-devel/manuals/v.net.steiner.html)
- [`v.to.db`](https://grass.osgeo.org/grass-devel/manuals/v.to.db.html)

---

## Authors

Maximilian Maldacker Mentor: Wolf Bergenheim

---

## Resources

- [Official v.net.visibility manual](https://grass.osgeo.org/grass-devel/manuals/v.net.visibility.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.visibility.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
