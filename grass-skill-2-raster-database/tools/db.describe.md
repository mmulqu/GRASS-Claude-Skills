# db.describe

**Category**: database

## Description

Describes a table in detail.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_describe(table,driver="sqlite",database="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",format="plain",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`table : str, required`**
   - Name of attribute table
   - Used as: input, dbtable, name

2. **`driver : str, optional`**
   - Name of database driver
   - Used as: input, dbdriver, name
   - Allowed values: dbf, odbc, ogr, pg, sqlite

3. **`database : str, optional`**
   - Name of database
   - Used as: input, dbname, name
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db

4. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/db.describe.html#__tabbed_2_3) for all details)*

5. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Print column names only instead of full column descriptions

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

db.describe displays table information. If parameter -c is used
only column names instead of full column descriptions is given.

---

## Note

If parameters for database connection are already set with db.connect , they are taken as default values and do not
need to be specified each time.

---

## See Also

Related tools:
- [`db.columns`](https://grass.osgeo.org/grass-devel/manuals/db.columns.html)
- [`db.droptable`](https://grass.osgeo.org/grass-devel/manuals/db.droptable.html)
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`db.login`](https://grass.osgeo.org/grass-devel/manuals/db.login.html)
- [`db.tables`](https://grass.osgeo.org/grass-devel/manuals/db.tables.html)

---

## Resources

- [Official db.describe manual](https://grass.osgeo.org/grass-devel/manuals/db.describe.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.describe.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
