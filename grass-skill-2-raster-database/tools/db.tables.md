# db.tables

**Category**: database

## Description

Lists all tables for a given database.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_tables(driver="sqlite",database="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`driver : str, optional`**
   - Name of database driver
   - Used as: input, dbdriver, name
   - Allowed values: dbf, odbc, ogr, pg, sqlite

2. **`database : str, optional`**
   - Name of database
   - Used as: input, dbname, name
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db

3. **`flags : str, optional`**
   - Allowed values: p, s
   - p
   - Print tables and exit
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/db.tables.html#__tabbed_2_3) for all details)*

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

db.tables lists all tables for a given database.

---

## Note

If parameters for database connection are already set with db.connect , they are taken as default values and do not
need to be specified each time.

---

## See Also

Related tools:
- [`db.columns`](https://grass.osgeo.org/grass-devel/manuals/db.columns.html)
- [`db.droptable`](https://grass.osgeo.org/grass-devel/manuals/db.droptable.html)
- [`db.login`](https://grass.osgeo.org/grass-devel/manuals/db.login.html)
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)

---

## Resources

- [Official db.tables manual](https://grass.osgeo.org/grass-devel/manuals/db.tables.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.tables.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
