# v.net.iso

**Category**: vector

## Description

Splits subnets for nearest centers by cost isolines. Splits net to bands between cost isolines (direction from center). Center node must be opened (costs >= 0). Costs of center node are used in calculation.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_net_iso(input,output,method="from",center_cats,costs,arc_layer="1",arc_type="line,boundary",node_layer="2",arc_column=None,arc_backward_column=None,node_column=None,turn_layer="3",turn_cat_layer="4",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`method : str, optional`**
   - Use costs from centers or costs to centers
   - Allowed values: from, to
   - Default: from

4. **`center_cats : str, required`**
   - Category values
   - Categories of centers (points on nodes) to which net will be allocated, layer for this categories is given by nlayer option
   - Used as: input, cats, range

5. **`costs : int | list[int] | str, required`**
   - Costs for isolines

6. **`arc_layer : str, required`**
   - Arc layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

7. **`arc_type : str | list[str], required`**
   - Arc type
   - Input feature type
   - Allowed values: line, boundary

8. **`node_layer : str, required`**
   - Node layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

9. **`arc_column : str, optional`**
   - Arc forward/both direction(s) cost column (number)
   - Used as: input, dbcolumn, name

10. **`arc_backward_column : str, optional`**
   - Arc backward direction cost column (number)
   - Used as: input, dbcolumn, name

11. **`node_column : str, optional`**
   - Node cost column (number)
   - Used as: input, dbcolumn, name

12. **`turn_layer : str, optional`**
   - Layer with turntable
   - Relevant only with -t flag
   - Used as: input, layer

13. **`turn_cat_layer : str, optional`**
   - Layer with unique categories used in turntable
   - Relevant only with -t flag
   - Used as: input, layer

14. **`flags : str, optional`**
   - Allowed values: t, g, u
   - t
   - Use turntable
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.net.iso.html#__tabbed_2_3) for all details)*

15. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

16. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

17. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

18. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 18 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.iso.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.net.iso splits a network into bands between cost isolines (distance
from center). Center nodes must be opened (costs >= 0). The costs of
center nodes are used in the calculation.

Costs may be either line lengths, or attributes saved in a database
table. These attribute values are taken as costs of whole segments, not
as costs to traverse a length unit (e.g. meter) of the segment. For
example, if the speed limit is 100 km / h, the cost to traverse a 10 km
long road segment must be calculated as length / speed = 10 km / (100 km/h) = 0.1 h. Supported are cost assignments for both arcs and nodes, and also
different costs for both directions of a vector line. For areas, costs
will be calculated along boundary lines.

The input vector needs to be prepared with v.net operation=connect in
order to connect points representing center nodes to the network.

The nearest center can be determined using either costs from the nearest
center or costs to the nearest center with option method .

By default, the iso band number is used as category value for output
lines. With the -u flag, output lines become unique categories and
an attribute table is created with the fields cat, ocat, center, isonr,
isolbl . The ocat field holds the original line category in arc_layer , the center field holds the center category in node_layer , the isonr field holds the iso band number and the isolbl field holds a label for the isoband. Additionally, original
line categories are copied from the input arc_layer to layer 2 in
the output, together with any attribute table.

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
- [`v.net.path`](https://grass.osgeo.org/grass-devel/manuals/v.net.path.html)
- [`v.net.salesman`](https://grass.osgeo.org/grass-devel/manuals/v.net.salesman.html)
- [`v.net.steiner`](https://grass.osgeo.org/grass-devel/manuals/v.net.steiner.html)
- [`v.patch`](https://grass.osgeo.org/grass-devel/manuals/v.patch.html)

---

## Authors

Radim Blazek, ITC-Irst, Trento, Italy Documentation: Markus Neteler, Markus Metz
The turns support was implemnented as part of GRASS GIS turns cost
project at Czech Technical University in Prague, Czech Republic. Eliska
Kyzlikova, Stepan Turek, Lukas Bocan and Viera Bejdova participated at
the project. Implementation: Stepan Turek Documentation: Lukas Bocan
Mentor: Martin Landa

---

## Resources

- [Official v.net.iso manual](https://grass.osgeo.org/grass-devel/manuals/v.net.iso.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.iso.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
