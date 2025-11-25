# v.db.update

**Category**: vector

## Description

Updates a column in the attribute table connected to a vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_db_update(map,layer="1",column,value=None,query_column=None,where=None,sqliteextra=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, required`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`column : str, required`**
   - Name of attribute column to update
   - Used as: input, dbcolumn, name

4. **`value : str, optional`**
   - Literal value to update the column with

5. **`query_column : str, optional`**
   - Name of other attribute column to query, can be combination of columns (e.g. co1+col2)
   - Used as: input, dbcolumn, name

6. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

7. **`sqliteextra : str, optional`**
   - Name of SQLite extension file for extra functions (SQLite backend only)
   - Used as: input, file, name

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

v.db.update assigns a new value to a column in the attribute table
connected to a given map. The value parameter allows updating with a
literal value. Alternatively, with the qcol parameter values can be
copied from another column in the table or be the result of a
combination or transformation of other columns.

---

## See Also

Related tools:
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`v.db.addcolumn`](https://grass.osgeo.org/grass-devel/manuals/v.db.addcolumn.html)
- [`v.db.addtable`](https://grass.osgeo.org/grass-devel/manuals/v.db.addtable.html)
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [`v.db.droptable`](https://grass.osgeo.org/grass-devel/manuals/v.db.droptable.html)
- [`v.db.join`](https://grass.osgeo.org/grass-devel/manuals/v.db.join.html)
- [`v.db.select`](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html)

---

## Resources

- [Official v.db.update manual](https://grass.osgeo.org/grass-devel/manuals/v.db.update.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.db.update.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
