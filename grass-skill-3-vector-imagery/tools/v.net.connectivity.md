# v.net.connectivity

**Category**: vector

## Description

Computes vertex connectivity between two sets of nodes in the network.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_net_connectivity(input,arc_layer="1",node_layer="2",arc_column=None,arc_backward_column=None,output,node_column=None,set1_cats=None,set1_where=None,set2_cats=None,set2_where=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

4. **`arc_column : str, optional`**
   - Arc forward/both direction(s) cost column (number)
   - Used as: input, dbcolumn, name

5. **`arc_backward_column : str, optional`**
   - Arc backward direction cost column (number)
   - Used as: input, dbcolumn, name

6. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

7. **`node_column : str, optional`**
   - Node cost column (number)
   - Used as: input, dbcolumn, name

8. **`set1_cats : str, optional`**
   - Set1 category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

9. **`set1_where : str, optional`**
   - Set1 WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

10. **`set2_cats : str, optional`**
   - Category values
   - Set2 category values
   - Used as: input, cats, range

11. **`set2_where : str, optional`**
   - Set2 WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

12. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

13. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

14. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

15. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.connectivity.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.net.connectivity computes vertex connectivity between two sets, i.e.
the minimum number of vertices whose removal would separate two given
sets.

---

## See Also

Related tools:
- [`v.net`](https://grass.osgeo.org/grass-devel/manuals/v.net.html)
- [`v.net.flow`](https://grass.osgeo.org/grass-devel/manuals/v.net.flow.html)
- [`v.net.bridge`](https://grass.osgeo.org/grass-devel/manuals/v.net.bridge.html)

---

## Authors

Daniel Bundala, Google Summer of Code 2009, Student Wolf Bergenheim, Mentor

---

## Resources

- [Official v.net.connectivity manual](https://grass.osgeo.org/grass-devel/manuals/v.net.connectivity.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.connectivity.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
