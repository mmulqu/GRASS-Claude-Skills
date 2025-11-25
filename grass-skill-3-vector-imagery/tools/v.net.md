# v.net

**Category**: vector

## Description

Performs network maintenance.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_net(input=None,points=None,output=None,operation,arc_layer="1",arc_type="line,boundary",node_layer="2",threshold=None,file=None,turn_layer="3",turn_cat_layer="4",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, optional`**
   - Name of input vector line map (arcs)
   - Required for operation 'nodes', 'connect', 'report' and 'nreport'
   - Used as: input, vector, name

2. **`points : str, optional`**
   - Name of input vector point map (nodes)
   - Required for operation 'connect' and 'arcs'
   - Used as: input, vector, name

3. **`output : str, optional`**
   - Name for output vector map
   - Used as: output, vector, name

4. **`operation : str, required`**
   - Operation to be performed
   - Allowed values: nodes, connect, arcs, report, nreport, turntable
   - nodes: new point is placed on each node (line end) if doesn't exist
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.net.html#__tabbed_2_3) for all details)*

5. **`arc_layer : str, optional`**
   - Arc layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: output, layer

6. **`arc_type : str | list[str], optional`**
   - Arc type
   - Input feature type
   - Allowed values: line, boundary

7. **`node_layer : str, optional`**
   - Node layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: output, layer

8. **`threshold : float, optional`**
   - Threshold
   - Required for operation 'connect'. Connect points in given threshold.

9. **`file : str | io.StringIO, optional`**
   - Name of input file
   - Required for operation 'arcs' ('-' for standard input)
   - Used as: input, file, name

10. **`turn_layer : str, optional`**
   - Turntable layer
   - Layer where turntable will be attached. Format: layer number[/layer name].Required for operation 'turntable'.
   - Used as: input, layer

11. **`turn_cat_layer : str, optional`**
   - Layer with unique categories used in turntable
   - Layer with unique categories for every line in arc_layer and point on every node.  The categories are used in turntable. Format: layer number[/layer name]. Required for operation 'turntable'.
   - Used as: input, layer

12. **`flags : str, optional`**
   - Allowed values: c, s
   - c
   - Assign unique categories to new points
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.net.html#__tabbed_2_3) for all details)*

13. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

14. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

15. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

16. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.net is used for network preparation and maintenance. Its main use is
to create a vector network from vector lines ( arcs ) and points
( nodes ) by creating nodes from intersections in a map of vector lines
( node operator), by connecting a vector lines map with a points map
( connect operator), and by creating new lines between pairs of vector
points ( arcs operator).

A GIS network consists of topologically correct lines (arcs). That is,
the lines must be connected by shared vertices where real connections
exist. In GRASS you also can add nodes to the network. These are
specially designated vertices used for analyzing network properties or
computing cost/distance measures. That is, not all vertices are
treated as nodes by default . Only v.net.path can
use a network without nodes, they are required for all the other network
modules. In GRASS, network arcs are stored in one data layer (normally
layer 1) and nodes are stored in a different data layer (normally layer
2).

v.net offers two ways to add nodes to a network of arcs and one method
to add arcs to a set of nodes:

While the arcs created with v.net will retain any attribute information
associated with the input vector line/boundary file in data layer 1,
nodes created and stored in data layer 2 will not have any associated
attribute information.

For nodes created using the connect and arcs operations (methods 1
and 3 above), the nodes can be reconnected to the attribute table of the
input vector points file using the attribute table manager ("manage
layers" tab) or by running v.db.connect .

For nodes created using the nodes operation (method 2 above), it is
possible to create an attribute table for the new nodes in layer 2 using
the attribute table manager and connect it to layer 2 ("manage layers"
tab) or to create a table with v.db.addtable ,
connect it to layer 2 with v.db.connect , and update
the new table with cat values with v.to.db .

The turntable operation creates a turntable with the costs for every
possible turn on every possible node (intersection, crossroad) in given
layer (arc_layer). U-turns are taken in account too. Turntable is
created in turn_layer and turn_cat_layer . Building the turntable
allows you to model e.g. traffic code, where some turns may be
prohibited. If features in analyzed network are changed, the turntable
must be created again (e.g. it includes v.net connect operation).
Turntable name consists of output vector map name + "_turntable_" +
"t" + "_" + turn_layer + "_" + "tuc" + "_" + turn_cat_layer + "_" +
"a" + "_" + arc_layer e. g. roads_turntable_t_3_tuc_4_a_1

These modules are able to work with the turntable: v.net.alloc , v.net.iso , v.net.path , v.net.salesman For
more information about turns in the vector network analyses see the
"turns" wiki
page .

Once a vector network has been created, it can be analyzed in a number
of powerful ways using the suite of v.net .* modules. The shortest
route between two nodes, following arcs, can be computed
( v.net.path ), as can the shortest route that will
pass through a set of nodes and return to the starting node
( v.net.salesman ). Least cost routes through the
network can be calculated on the basis of distance only or on the basis
of distance weighted by an attribute associated with each arc (for
example, travel speed along a network segment). A network can be divided
into concentric zones of equal travel cost around one or more nodes
( v.net.iso ) or subdivided so that each node is
surrounded by a zone in which all arcs can be reached with the same
travel costs as all arcs surrounding each other node
( v.net.alloc ). In addition to the modules listed
above, the GRASS vector networking suite includes numerous other modules
for analysis of network costs and connectivity. These include: v.net.allpairs , v.net.bridge , v.net.centrality , v.net.components , v.net.distance , v.net.flow , v.net.spanningtree , v.net.steiner , v.net.timetable , v.net.visibility

---

## See Also

Related tools:
- [`g.gui.vdigit`](https://grass.osgeo.org/grass-devel/manuals/g.gui.vdigit.html)
- [`v.edit`](https://grass.osgeo.org/grass-devel/manuals/v.edit.html)

---

## Authors

Radim Blazek, ITC-irst, Trento, Italy Martin Landa, FBK-irst (formerly ITC-irst), Trento, Italy and CTU in
Prague, Czech Republic (operation 'connect' and 'arcs') Markus Metz: important fixes and improvements
The turns support was implemnented as part of GRASS GIS turns cost
project at Czech Technical University in Prague, Czech Republic. Eliska
Kyzlikova, Stepan Turek, Lukas Bocan and Viera Bejdova participated at
the project. Implementation: Stepan Turek Documentation: Lukas Bocan
Mentor: Martin Landa

---

## Resources

- [Official v.net manual](https://grass.osgeo.org/grass-devel/manuals/v.net.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
