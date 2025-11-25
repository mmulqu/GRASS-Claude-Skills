# v.net.steiner

**Category**: vector

## Description

Creates Steiner tree for the network and given terminals. Note that 'Minimum Steiner Tree' problem is NP-hard and heuristic algorithm is used in this module so the result may be sub optimal.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_net_steiner(input,output,arc_type="line,boundary",arc_layer="1",node_layer="2",acolumn=None,terminal_cats,npoints=-1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`arc_type : str | list[str], optional`**
   - Arc type
   - Input feature type
   - Allowed values: line, boundary

4. **`arc_layer : str, optional`**
   - Arc layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

5. **`node_layer : str, optional`**
   - Node layer (used for terminals)
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

6. **`acolumn : str, optional`**
   - Arcs' cost column (for both directions)

7. **`terminal_cats : str, required`**
   - Category values
   - Categories of points on terminals (layer is specified by nlayer)
   - Used as: input, cats, range

8. **`npoints : int, optional`**
   - Number of Steiner points (-1 for all possible)
   - Default: -1

9. **`flags : str, optional`**
   - Allowed values: g
   - g
   - Use geodesic calculation for longitude-latitude projects

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.steiner.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.net.steiner calculates the optimal connection of nodes on a vector
network.

A Steiner tree is used to calculate the minimum-cost vector network
connecting some number of end nodes in a network framework. For example
it could be used to find the path following a road system which will
minimize the amount of fibre optic cable needed to connect a series of
satellite offices.

Costs may be either line lengths, or attributes saved in a database
table. These attribute values are taken as costs of whole segments, not
as costs to traverse a length unit (e.g. meter) of the segment. For
example, if the speed limit is 100 km / h, the cost to traverse a 10 km
long road segment must be calculated as length / speed = 10 km / (100
km/h) = 0.1 h. Supported are cost assignments for both arcs and nodes.
For areas, costs will be calculated along boundary lines.

Points representing nodes must be exactly on network nodes, and the
input vector map needs to be prepared with v.net operation=connect .

---

## See Also

Related tools:
- [`d.path`](https://grass.osgeo.org/grass-devel/manuals/d.path.html)
- [`v.net`](https://grass.osgeo.org/grass-devel/manuals/v.net.html)
- [`v.net.alloc`](https://grass.osgeo.org/grass-devel/manuals/v.net.alloc.html)
- [`v.net.iso`](https://grass.osgeo.org/grass-devel/manuals/v.net.iso.html)
- [`v.net.path`](https://grass.osgeo.org/grass-devel/manuals/v.net.path.html)
- [`v.net.salesman`](https://grass.osgeo.org/grass-devel/manuals/v.net.salesman.html)

---

## Authors

Radim Blazek, ITC-Irst, Trento, Italy Documentation: Markus Neteler, Markus Metz

---

## Resources

- [Official v.net.steiner manual](https://grass.osgeo.org/grass-devel/manuals/v.net.steiner.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.steiner.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
