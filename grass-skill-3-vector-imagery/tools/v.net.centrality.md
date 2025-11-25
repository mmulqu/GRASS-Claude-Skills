# v.net.centrality

**Category**: vector

## Description

Computes degree, centrality, betweeness, closeness and eigenvector centrality measures in the network.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_net_centrality(input,arc_layer="1",node_layer="2",output,cats=None,where=None,arc_column=None,arc_backward_column=None,node_column=None,degree=None,closeness=None,betweenness=None,eigenvector=None,iterations=1000,error=0.1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

5. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

6. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

7. **`arc_column : str, optional`**
   - Arc forward/both direction(s) cost column (number)
   - Used as: input, dbcolumn, name

8. **`arc_backward_column : str, optional`**
   - Arc backward direction cost column (number)
   - Used as: input, dbcolumn, name

9. **`node_column : str, optional`**
   - Node cost column (number)

10. **`degree : str, optional`**
   - Name of degree centrality column
   - Used as: input, dbcolumn, name

11. **`closeness : str, optional`**
   - Name of closeness centrality column
   - Used as: input, dbcolumn, name

12. **`betweenness : str, optional`**
   - Name of betweenness centrality column
   - Used as: input, dbcolumn, name

13. **`eigenvector : str, optional`**
   - Name of eigenvector centrality column
   - Used as: input, dbcolumn, name

14. **`iterations : int, optional`**
   - Maximum number of iterations to compute eigenvector centrality
   - Default: 1000

15. **`error : float, optional`**
   - Cumulative error tolerance for eigenvector centrality
   - Default: 0.1

16. **`flags : str, optional`**
   - Allowed values: g, a
   - g
   - Use geodesic calculation for longitude-latitude projects
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.net.centrality.html#__tabbed_2_3) for all details)*

17. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

18. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

19. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

20. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 20 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.centrality.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.net.centrality computes degree, closeness, betweenness and
eigenvector centrality measures.

---

## See Also

Related tools:
- [`v.net`](https://grass.osgeo.org/grass-devel/manuals/v.net.html)
- [`v.generalize`](https://grass.osgeo.org/grass-devel/manuals/v.generalize.html)

---

## Authors

Daniel Bundala, Google Summer of Code 2009, Student Wolf Bergenheim, Mentor

---

## Resources

- [Official v.net.centrality manual](https://grass.osgeo.org/grass-devel/manuals/v.net.centrality.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.centrality.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
