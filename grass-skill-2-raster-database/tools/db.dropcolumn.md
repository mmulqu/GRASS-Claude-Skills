# db.dropcolumn

**Category**: database

## Description

Drops a column from selected attribute table.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_dropcolumn(table,column,database=None,driver=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`table : str, required`**
   - Name of attribute table
   - Used as: input, dbtable, name

2. **`column : str, required`**
   - Name of attribute column
   - Used as: input, dbcolumn, name

3. **`database : str, optional`**
   - Name of database
   - Used as: input, dbname, name

4. **`driver : str, optional`**
   - Name of database driver
   - Used as: input, dbdriver, name
   - Allowed values: dbf, odbc, ogr, sqlite, pg

5. **`flags : str, optional`**
   - Allowed values: f
   - f
   - Force removal (required for actual deletion of files)

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

db.dropcolumn drops a column from an attribute table. If the -f force flag is not given then nothing is removed, instead a preview of
the action to be taken is printed.

---

## See Also

Related tools:
- [`db.describe`](https://grass.osgeo.org/grass-devel/manuals/db.describe.html)
- [`db.droptable`](https://grass.osgeo.org/grass-devel/manuals/db.droptable.html)
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`v.db.dropcolumn`](https://grass.osgeo.org/grass-devel/manuals/v.db.dropcolumn.html)

---

## Resources

- [Official db.dropcolumn manual](https://grass.osgeo.org/grass-devel/manuals/db.dropcolumn.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.dropcolumn.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
