# v.what.rast3

**Category**: vector

## Description

Uploads 3D raster values at positions of vector points to the table.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_what_rast3(map,layer="1",raster_3d,column,where=None,verbose=None,quiet=None,superquiet=None)
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

3. **`raster_3d : str, required`**
   - Name of existing 3D raster map to be queried
   - Used as: input, raster_3d, name

4. **`column : str, required`**
   - Name of attribute column to be updated with the query result
   - Used as: input, dbcolumn, name

5. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
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

v.what.rast3 reads 3D raster value for each point in the vector and
updates col column in vector attribute table by this value. The
column should be type double. This module is based on v.what.rast . If more points have the same category, attribute value is set to NULL.
If 3D raster values is NULL, attribute value is set to NULL.

---

## See Also

Related tools:
- [`v.db.addtable`](https://grass.osgeo.org/grass-devel/manuals/v.db.addtable.html)
- [`v.db.select`](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html)
- [`v.what.rast`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html)
- [`v.what.vect`](https://grass.osgeo.org/grass-devel/manuals/v.what.vect.html)
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)

---

## Resources

- [Official v.what.rast3 manual](https://grass.osgeo.org/grass-devel/manuals/v.what.rast3.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.what.rast3.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
