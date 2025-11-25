# v.db.join

**Category**: vector

## Description

Joins a database table to a vector map table.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_db_join(map,layer="1",column,other_table,other_column,subset_columns=None,exclude_columns=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Vector map to which to join other table
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Layer where to join
   - Used as: input, layer

3. **`column : str, required`**
   - Identifier column (e.g.: cat) in the vector table to be used for join
   - Used as: input, dbcolumn, name

4. **`other_table : str, required`**
   - Other table name
   - Used as: input, dbtable, name

5. **`other_column : str, required`**
   - Identifier column (e.g.: id) in the other table used for join
   - Used as: input, dbcolumn, name

6. **`subset_columns : str | list[str], optional`**
   - Subset of columns from the other table
   - Used as: input, dbcolumn, name

7. **`exclude_columns : str | list[str], optional`**
   - Columns to exclude from the other table
   - Used as: input, dbcolumn, name

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

v.db.join joins the content of another table into the connected
attribute table of a vector map.

---

## See Also

Related tools:
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`db.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/db.in.ogr.html)
- [`db.select`](https://grass.osgeo.org/grass-devel/manuals/db.select.html)
- [`v.db.update`](https://grass.osgeo.org/grass-devel/manuals/v.db.update.html)

---

## Resources

- [Official v.db.join manual](https://grass.osgeo.org/grass-devel/manuals/v.db.join.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.db.join.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
