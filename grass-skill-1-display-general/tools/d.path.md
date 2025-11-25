# d.path

**Category**: display

## Description

Finds shortest path for selected starting and ending node.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_path(map,arc_type="line,boundary",coordinates,arc_layer="1",node_layer="2",arc_column=None,arc_backward_column=None,node_column=None,highlight_color="red",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`arc_type : str | list[str], optional`**
   - Arc type
   - Allowed values: line, boundary
   - Default: line,boundary

3. **`coordinates : tuple[float, float, float, float] | list[float] | str, required`**
   - Starting and ending coordinates
   - Used as: input, coords, x1,y1,x2,y2

4. **`arc_layer : str, optional`**
   - Arc layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

5. **`node_layer : str, optional`**
   - Node layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

6. **`arc_column : str, optional`**
   - Arc forward/both direction(s) cost column (number)

7. **`arc_backward_column : str, optional`**
   - Arc backward direction cost column (number)

8. **`node_column : str, optional`**
   - Node cost column

9. **`highlight_color : str, optional`**
   - Highlight color
   - Used as: color
   - Default: red

10. **`flags : str, optional`**
   - Allowed values: g, b
   - g
   - Use geodesic calculation for longitude-latitude locations
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.path.html#__tabbed_2_3) for all details)*

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.path.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.path enables shortest path vector networking. Costs may be either
line lengths, or attributes saved in a database table. Supported are
cost assignments for both arcs and nodes, and also different in both
directions of a vector line. For areas cost will be calculated along
boundary lines.

---

## Note

The user needs to display a vector map before using d.path. If no
graphics monitor is open, a file map.png is generated in the current
directory.

The 'from' and 'to' points are entered by mouse into the map displayed
in the GRASS monitor, or if the coordinates option is used they can
be specified non-interactively. The actions bound to the mouse buttons
are described in the terminal window when running the command.

To calculate shortest path non-interactively and save the path to a new
vector map, use the v.net.path module.

---

## See Also

Related tools:
- [`v.net.path`](https://grass.osgeo.org/grass-devel/manuals/v.net.path.html)

---

## Resources

- [Official d.path manual](https://grass.osgeo.org/grass-devel/manuals/d.path.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.path.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
