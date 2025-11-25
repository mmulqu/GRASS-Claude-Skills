# v.net.flow

**Category**: vector

## Description

Computes the maximum flow between two sets of nodes in the network.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_net_flow(input,arc_layer="1",node_layer="2",output,cut,arc_column=None,arc_backward_column=None,node_column=None,source_cats=None,source_where=None,sink_cats=None,sink_where=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`arc_layer : str, optional`**
   - Arc layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`node_layer : str, optional`**
   - Node layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

4. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

5. **`cut : str, required`**
   - Name for output vector map containing a minimum cut
   - Used as: output, vector, name

6. **`arc_column : str, optional`**
   - Arc forward/both direction(s) cost column (number)
   - Used as: input, dbcolumn, name

7. **`arc_backward_column : str, optional`**
   - Arc backward direction cost column (number)
   - Used as: input, dbcolumn, name

8. **`node_column : str, optional`**
   - Node cost column (number)
   - Used as: input, dbcolumn, name

9. **`source_cats : str, optional`**
   - Source category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

10. **`source_where : str, optional`**
   - Source WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

11. **`sink_cats : str, optional`**
   - Sink category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

12. **`sink_where : str, optional`**
   - Sink WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

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


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.flow.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.net.flow computes the maximum flow and minimum cut between two sets
of nodes.

---

## See Also

Related tools:
- [`v.net`](https://grass.osgeo.org/grass-devel/manuals/v.net.html)
- [`v.net.connectivity`](https://grass.osgeo.org/grass-devel/manuals/v.net.connectivity.html)

---

## Authors

Daniel Bundala, Google Summer of Code 2009, Student Wolf Bergenheim, Mentor

---

## Resources

- [Official v.net.flow manual](https://grass.osgeo.org/grass-devel/manuals/v.net.flow.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.flow.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
