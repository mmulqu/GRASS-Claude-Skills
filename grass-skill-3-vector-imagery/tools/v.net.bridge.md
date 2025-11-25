# v.net.bridge

**Category**: vector

## Description

Computes bridges and articulation points in the network.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_net_bridge(input,output,arc_layer="1",node_layer="2",arc_column=None,arc_backward_column=None,node_column=None,method,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

4. **`node_layer : str, optional`**
   - Node layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

5. **`arc_column : str, optional`**
   - Arc forward/both direction(s) cost column (number)
   - Used as: input, dbcolumn, name

6. **`arc_backward_column : str, optional`**
   - Arc backward direction cost column (number)
   - Used as: input, dbcolumn, name

7. **`node_column : str, optional`**
   - Node cost column (number)

8. **`method : str, required`**
   - Feature type
   - Allowed values: bridge, articulation
   - bridge: Finds bridges

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.bridge.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.net.bridge finds bridges and articulation points in a network.

---

## See Also

Related tools:
- [`v.net`](https://grass.osgeo.org/grass-devel/manuals/v.net.html)
- [`v.category`](https://grass.osgeo.org/grass-devel/manuals/v.category.html)

---

## Authors

Daniel Bundala, Google Summer of Code 2009, Student Wolf Bergenheim, Mentor

---

## Resources

- [Official v.net.bridge manual](https://grass.osgeo.org/grass-devel/manuals/v.net.bridge.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.bridge.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
