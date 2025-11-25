# db.copy

**Category**: database

## Description

Copy a table. Either 'from_table' (optionally with 'where') can be used or 'select' option, but not 'from_table' and 'select' at the same time.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_copy(from_driver="sqlite",from_database="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",from_table=None,to_driver="sqlite",to_database="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",to_table,where=None,select=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`from_driver : str, optional`**
   - Input driver name
   - Used as: input, dbdriver, name
   - Allowed values: dbf, odbc, ogr, pg, sqlite

2. **`from_database : str, optional`**
   - Input database name
   - Used as: input, dbname, name
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db

3. **`from_table : str, optional`**
   - Input table name (only, if 'select' is not used)
   - Used as: input, dbtable, name

4. **`to_driver : str, optional`**
   - Output driver name
   - Used as: input, dbdriver, name
   - Allowed values: dbf, odbc, ogr, pg, sqlite

5. **`to_database : str, optional`**
   - Output database name
   - Used as: input, dbname, name
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db

6. **`to_table : str, required`**
   - Output table name
   - Used as: output, dbtable, name

7. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

8. **`select : str, optional`**
   - Full select statement (only, if 'from_table' and 'where' is not used)
   - E.g.: SELECT dedek FROM starobince WHERE obec = 'Frimburg'

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


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/db.copy.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

db.copy allows the user to copy a table between two databases.
Databases can be connected through different drivers (see examples
below).

---

## See Also

Related tools:
- [`db.connect`](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [`db.drivers`](https://grass.osgeo.org/grass-devel/manuals/db.drivers.html)
- [`db.login`](https://grass.osgeo.org/grass-devel/manuals/db.login.html)
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [`v.clean`](https://grass.osgeo.org/grass-devel/manuals/v.clean.html)

---

## Resources

- [Official db.copy manual](https://grass.osgeo.org/grass-devel/manuals/db.copy.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.copy.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
