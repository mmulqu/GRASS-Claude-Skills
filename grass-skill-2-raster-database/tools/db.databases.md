# db.databases

**Category**: database

## Description

Lists all databases for a given driver and location.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_databases(driver="sqlite",location=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`driver : str, optional`**
   - Name of database driver
   - Used as: input, dbdriver, name
   - Allowed values: dbf, odbc, ogr, pg, sqlite

2. **`location : str, optional`**
   - Location
   - Path for SQLite driver, or connection string for PostgreSQL driver
   - Used as: name

3. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

4. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

5. **`superquiet : bool, optional`**
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

db.databases lists all databases for a given driver and optionally location .

---

## See Also

Related tools:
- [`db.columns`](https://grass.osgeo.org/grass-devel/manuals/db.columns.html)
- [`db.describe`](https://grass.osgeo.org/grass-devel/manuals/db.describe.html)
- [`db.drivers`](https://grass.osgeo.org/grass-devel/manuals/db.drivers.html)
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`db.login`](https://grass.osgeo.org/grass-devel/manuals/db.login.html)
- [`db.tables`](https://grass.osgeo.org/grass-devel/manuals/db.tables.html)

---

## Authors

Radim Blazek, ITC-Irst, Trento, Italy Updated for GRASS 7 by Martin Landa, Czech Technical University in
Prague, Czech Republic

---

## Resources

- [Official db.databases manual](https://grass.osgeo.org/grass-devel/manuals/db.databases.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.databases.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
