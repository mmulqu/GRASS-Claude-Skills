# v.db.dropcolumn

**Category**: vector

## Description

Drops a column from the attribute table connected to a given vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_db_dropcolumn(map,layer="1",columns,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`columns : str | list[str], required`**
   - Name of attribute column(s) to drop
   - Used as: input, dbcolumn, name

4. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

5. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

6. **`superquiet : bool, optional`**
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

v.db.dropcolumn drops a column from the attribute table connected to a
given vector map. It automatically checks the connection for the
specified layer. v.db.dropcolumn omits to delete the 'cat' column
which is relevant to keep the connection between vector map and table.

---

## See Also

Related tools:
- [`db.connect`](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [`db.dropcolumn`](https://grass.osgeo.org/grass-devel/manuals/db.dropcolumn.html)
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`v.db.addcolumn`](https://grass.osgeo.org/grass-devel/manuals/v.db.addcolumn.html)
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [`v.db.droptable`](https://grass.osgeo.org/grass-devel/manuals/v.db.droptable.html)
- [`v.db.select`](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html)
- [`v.db.update`](https://grass.osgeo.org/grass-devel/manuals/v.db.update.html)

---

## Resources

- [Official v.db.dropcolumn manual](https://grass.osgeo.org/grass-devel/manuals/v.db.dropcolumn.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.db.dropcolumn.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
