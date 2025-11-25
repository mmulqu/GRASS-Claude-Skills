# db.connect

**Category**: database

## Description

Prints/sets general DB connection for current mapset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_connect(driver="sqlite",database="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",schema=None,group=None,format="plain",flags=None,verbose=None,quiet=None,superquiet=None)
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

3. **`schema : str, optional`**
   - Database schema
   - Do not use this option if schemas are not supported by driver/database server
   - Used as: name

4. **`group : str, optional`**
   - Default group of database users to which select privilege is granted

5. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, shell, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/db.connect.html#__tabbed_2_3) for all details)*

6. **`flags : str, optional`**
   - Allowed values: p, g, c, d
   - p
   - Print current connection parameters and exit

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

db.connect allows the user to set database connection parameters.
These parameters are then taken as default values by modules so that the
user does not need to enter the parameters each time.

The default database backend in GRASS is SQLite (since version 7).

---

## See Also

Related tools:
- [`db.columns`](https://grass.osgeo.org/grass-devel/manuals/db.columns.html)
- [`db.copy`](https://grass.osgeo.org/grass-devel/manuals/db.copy.html)
- [`db.drivers`](https://grass.osgeo.org/grass-devel/manuals/db.drivers.html)
- [`db.login`](https://grass.osgeo.org/grass-devel/manuals/db.login.html)
- [`db.tables`](https://grass.osgeo.org/grass-devel/manuals/db.tables.html)
- [`v.db.addtable`](https://grass.osgeo.org/grass-devel/manuals/v.db.addtable.html)
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)

---

## Authors

Main author: Radim Blazek, ITC-Irst, Trento, Italy GRASS 7 improvements: Martin Landa, Markus Metz

---

## Resources

- [Official db.connect manual](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.connect.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
