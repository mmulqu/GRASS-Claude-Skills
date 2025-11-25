# v.net.path

**Category**: vector

## Description

Finds shortest path on vector network.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_net_path(input,output,arc_layer="1",arc_type="line,boundary",node_layer="2",file=None,arc_column=None,arc_backward_column=None,node_column=None,dmax=1000,turn_layer="3",turn_cat_layer="4",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`arc_layer : str, required`**
   - Arc layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

4. **`arc_type : str | list[str], required`**
   - Arc type
   - Input feature type
   - Allowed values: line, boundary

5. **`node_layer : str, required`**
   - Node layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

6. **`file : str | io.StringIO, optional`**
   - Name of file containing start and end points. If not given, read from stdin
   - Used as: input, file, name

7. **`arc_column : str, optional`**
   - Arc forward/both direction(s) cost column (number)

8. **`arc_backward_column : str, optional`**
   - Arc backward direction cost column (number)

9. **`node_column : str, optional`**
   - Node cost column (number)

10. **`dmax : float, optional`**
   - Maximum distance to the network
   - If start/end are given as coordinates. If start/end point is outside this threshold, the path is not found and error message is printed. To speed up the process, keep this value as low as possible.
   - Default: 1000

11. **`turn_layer : str, optional`**
   - Layer with turntable
   - Relevant only with -t flag
   - Used as: input, layer

12. **`turn_cat_layer : str, optional`**
   - Layer with unique categories used in turntable
   - Relevant only with -t flag
   - Used as: input, layer

13. **`flags : str, optional`**
   - Allowed values: t, g, s
   - t
   - Use turntable
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.net.path.html#__tabbed_2_3) for all details)*

14. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

15. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

16. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

17. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 17 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.path.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.net.path determines least costly, e.g. shortest or fastest path(s)
on a vector network.

Costs may be either line lengths, or attributes saved in a database
table. These attribute values are taken as costs of whole segments, not
as costs to traverse a length unit (e.g. meter) of the segment. For
example, if the speed limit is 100 km / h, the cost to traverse a 10 km
long road segment must be calculated as

Supported are cost assignments for both arcs and nodes, and also
different costs for both directions of a vector line. For areas, costs
will be calculated along boundary lines.

The input vector needs to be prepared with v.net operation=connect in
order to connect points representing center nodes to the network.

Nodes and arcs can be closed using cost = -1 .

Least cost paths are written to the output vector map with an attached
attribute table.

Nodes can be

The syntax is as follows:

(Example: 1 1 2)

or

Points specified by category must be exactly on network nodes, and the
input vector map needs to be prepared with v.net operation=connect .

When specifying coordinates, the next network node to a given coordinate
pair is used.

The attribute table will contain the following attributes:

Application of flag -t enables a turntable support. This flag
requires additional parameters turn_layer and turn_cat_layer that are otherwise ignored. The turntable allows to model e.g. traffic
code, where some turns may be prohibited. This means that the input
layer is expanded by turntable with costs of every possible turn on any
possible node (intersection) in both directions. Turntable can be
created by the v.net module. For more information about
turns in the vector network analyses see wiki
page .

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

Radim Blazek, ITC-Irst, Trento, Italy Documentation: Markus Neteler, Markus Metz
The turns support was implemnented as part of GRASS GIS turns cost
project at Czech Technical University in Prague, Czech Republic.
Implementation: Stepan Turek Documentation: Lukas Bocan, Eliska Kyzlikova, Viera Bejdova Mentor: Martin Landa

---

## Resources

- [Official v.net.path manual](https://grass.osgeo.org/grass-devel/manuals/v.net.path.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.path.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
