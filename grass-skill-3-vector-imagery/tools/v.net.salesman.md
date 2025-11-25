# v.net.salesman

**Category**: vector

## Description

Creates a cycle connecting given nodes (Traveling salesman problem). Note that TSP is NP-hard, heuristic algorithm is used by this module and created cycle may be sub optimal

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_net_salesman(input,output,center_cats,arc_layer="1",arc_type="line,boundary",node_layer="2",arc_column=None,arc_backward_column=None,turn_layer="3",turn_cat_layer="4",sequence=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`center_cats : str, required`**
   - Category values
   - Categories of points ('cities') on nodes (layer is specified by nlayer)
   - Used as: input, cats, range

4. **`arc_layer : str, required`**
   - Arc layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

5. **`arc_type : str | list[str], required`**
   - Arc type
   - Input feature type
   - Allowed values: line, boundary

6. **`node_layer : str, required`**
   - Node layer (used for cities)
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

7. **`arc_column : str, optional`**
   - Arc forward/both direction(s) cost column (number)

8. **`arc_backward_column : str, optional`**
   - EXPERIMENTAL: Arc backward direction cost column (number)

9. **`turn_layer : str, optional`**
   - Layer with turntable
   - Relevant only with -t flag
   - Used as: input, layer

10. **`turn_cat_layer : str, optional`**
   - Layer with unique categories used in turntable
   - Relevant only with -t flag
   - Used as: input, layer

11. **`sequence : str, optional`**
   - Name for output file holding node sequence ("-" for stdout)
   - Used as: output, file, name

12. **`flags : str, optional`**
   - Allowed values: t, g
   - t
   - Use turntable
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.net.salesman.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.salesman.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.net.salesman calculates the optimal route to visit nodes on a vector
network.

Costs may be either line lengths or attributes saved in a database
table. These attribute values are taken as costs of whole segments, not
as costs to traverse a length unit (e.g. meter) of the segment. For
example, if the speed limit is 100 km / h, the cost to traverse a 10 km
long road segment must be calculated as length / speed = 10 km / (100 km/h) = 0.1 h. Supported are cost assignments for arcs, and also different costs for
both directions of a vector line. For areas, costs will be calculated
along boundary lines.

The input vector needs to be prepared with v.net operation=connect in
order to connect points representing center nodes to the network.

Points specified by category must be exactly on network nodes, and the
input vector map needs to be prepared with v.net operation=connect .

The flag -t enables turntable support. This flag requires additional
parameters, turn_layer and turn_cat_layer , that are otherwise
ignored. The turntable allows to model e.g. traffic code, where some
turns may be prohibited. This means that the input layer is expanded by
turntable with costs of every possible turn on any possible node
(intersection) in both directions. Turntable can be created by the v.net module. For more information about turns in the
vector network analyses see wiki
page .

---

## See Also

Related tools:
- [`d.path`](https://grass.osgeo.org/grass-devel/manuals/d.path.html)
- [`v.net`](https://grass.osgeo.org/grass-devel/manuals/v.net.html)
- [`v.net.alloc`](https://grass.osgeo.org/grass-devel/manuals/v.net.alloc.html)
- [`v.net.iso`](https://grass.osgeo.org/grass-devel/manuals/v.net.iso.html)
- [`v.net.path`](https://grass.osgeo.org/grass-devel/manuals/v.net.path.html)
- [`v.net.steiner`](https://grass.osgeo.org/grass-devel/manuals/v.net.steiner.html)

---

## Authors

Radim Blazek, ITC-Irst, Trento, Italy Markus Metz Documentation: Markus Neteler, Markus Metz
The turns support was implemented as part of GRASS GIS turns cost
project at Czech Technical University in Prague, Czech Republic. Eliska Kyzlikova, Stepan Turek, Lukas Bocan and Viera Bejdova
participated in the project.
Implementation: Stepan Turek Documentation: Lukas Bocan Mentor: Martin Landa

---

## Resources

- [Official v.net.salesman manual](https://grass.osgeo.org/grass-devel/manuals/v.net.salesman.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.salesman.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
