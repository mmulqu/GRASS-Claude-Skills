# v.net.distance

**Category**: vector

## Description

Computes shortest distance via the network between the given sets of features. Finds the shortest paths from each 'from' point to the nearest 'to' feature and various information about this relation are uploaded to the attribute table.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_net_distance(input,output,arc_layer="1",arc_type="line,boundary",node_layer="2",from_layer="1",from_cats=None,from_where=None,to_layer="1",to_type="point",to_cats=None,to_where=None,arc_column=None,arc_backward_column=None,node_column=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`arc_layer : str, optional`**
   - Arc layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

4. **`arc_type : str | list[str], optional`**
   - Arc type
   - Input feature type
   - Allowed values: line, boundary

5. **`node_layer : str, optional`**
   - Node layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

6. **`from_layer : str, optional`**
   - From layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

7. **`from_cats : str, optional`**
   - From category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

8. **`from_where : str, optional`**
   - From WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

9. **`to_layer : str, optional`**
   - Layer number or name
   - To layer number or name
   - Used as: input, layer

10. **`to_type : str | list[str], optional`**
   - To feature type
   - Allowed values: point, line, boundary
   - Default: point

11. **`to_cats : str, optional`**
   - To category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

12. **`to_where : str, optional`**
   - To WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

13. **`arc_column : str, optional`**
   - Arc forward/both direction(s) cost column (number)
   - Used as: input, dbcolumn, name

14. **`arc_backward_column : str, optional`**
   - Arc backward direction cost column (number)
   - Used as: input, dbcolumn, name

15. **`node_column : str, optional`**
   - Node cost column (number)
   - Used as: input, dbcolumn, name

16. **`flags : str, optional`**
   - Allowed values: g, l
   - g
   - Use geodesic calculation for longitude-latitude projects
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.net.distance.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 20 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.distance.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.net.distance finds the nearest element in set to for every point
in set from .

---

## See Also

Related tools:
- [`v.net.path`](https://grass.osgeo.org/grass-devel/manuals/v.net.path.html)
- [`v.net.allpairs`](https://grass.osgeo.org/grass-devel/manuals/v.net.allpairs.html)
- [`v.net.distance`](https://grass.osgeo.org/grass-devel/manuals/v.net.distance.html)
- [`v.net.alloc`](https://grass.osgeo.org/grass-devel/manuals/v.net.alloc.html)

---

## Authors

Daniel Bundala, Google Summer of Code 2009, Student Wolf Bergenheim, Mentor Markus Metz

---

## Resources

- [Official v.net.distance manual](https://grass.osgeo.org/grass-devel/manuals/v.net.distance.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.distance.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
