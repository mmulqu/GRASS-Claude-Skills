# db.execute

**Category**: database

## Description

Executes any SQL statement. For SELECT statements use 'db.select'.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_execute(sql=None,input=None,driver="sqlite",database="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",schema=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`sql : str, optional`**
   - SQL statement
   - Example: update rybniky set kapri = 'hodne' where kapri = 'malo'
   - Used as: sql_query

2. **`input : str | io.StringIO, optional`**
   - Name of file containing SQL statement(s)
   - '-' for standard input
   - Used as: input, file, name

3. **`driver : str, optional`**
   - Name of database driver
   - Used as: input, dbdriver, name
   - Allowed values: dbf, odbc, ogr, pg, sqlite

4. **`database : str, optional`**
   - Name of database
   - Used as: input, dbname, name
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db

5. **`schema : str, optional`**
   - Database schema
   - Do not use this option if schemas are not supported by driver/database server
   - Used as: name

6. **`flags : str, optional`**
   - Allowed values: i
   - i
   - Ignore SQL errors and continue

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

db.execute allows the user to execute SQL statements.

---

## See Also

Related tools:
- [`db.columns`](https://grass.osgeo.org/grass-devel/manuals/db.columns.html)
- [`db.describe`](https://grass.osgeo.org/grass-devel/manuals/db.describe.html)
- [`db.drivers`](https://grass.osgeo.org/grass-devel/manuals/db.drivers.html)
- [`db.droptable`](https://grass.osgeo.org/grass-devel/manuals/db.droptable.html)
- [`db.login`](https://grass.osgeo.org/grass-devel/manuals/db.login.html)
- [`db.select`](https://grass.osgeo.org/grass-devel/manuals/db.select.html)
- [`db.tables`](https://grass.osgeo.org/grass-devel/manuals/db.tables.html)

---

## Resources

- [Official db.execute manual](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.execute.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
