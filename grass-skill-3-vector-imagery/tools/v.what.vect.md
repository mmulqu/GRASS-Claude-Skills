# v.what.vect

**Category**: vector

## Description

Uploads vector values at positions of vector points to the table.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_what_vect(map,layer="1",column,query_map,query_layer="1",query_column,dmax=0.0,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector points map for which to edit attributes
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`column : str, required`**
   - Name of attribute column to be updated with the query result
   - Used as: input, dbcolumn, name

4. **`query_map : str, required`**
   - Name of vector map to be queried
   - Or data source for direct OGR access
   - Used as: input, vector, name

5. **`query_layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

6. **`query_column : str, required`**
   - Name of attribute column to be queried
   - Used as: input, dbcolumn, name

7. **`dmax : float, optional`**
   - Maximum query distance in map units (meters for ll)
   - Default: 0.0

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.what.vect transfers attributes from the query_map 's attribute
table into the map 's attribute table. The module can be used to
transfer attributes from the table of a polygon map into the attribute
table of a point vector map, as well as the other way around, i.e., from
a point map into the attribute table of a polygon map (See examples).
The script is based on v.distance .

---

## See Also

Related tools:
- [`v.db.addcolumn`](https://grass.osgeo.org/grass-devel/manuals/v.db.addcolumn.html)
- [`v.db.select`](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html)
- [`v.distance`](https://grass.osgeo.org/grass-devel/manuals/v.distance.html)
- [`v.rast.stats`](https://grass.osgeo.org/grass-devel/manuals/v.rast.stats.html)
- [`v.what.rast`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html)
- [`v.what.rast3`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast3.html)
- [`v.vect.stats`](https://grass.osgeo.org/grass-devel/manuals/v.vect.stats.html)

---

## Resources

- [Official v.what.vect manual](https://grass.osgeo.org/grass-devel/manuals/v.what.vect.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.what.vect.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
