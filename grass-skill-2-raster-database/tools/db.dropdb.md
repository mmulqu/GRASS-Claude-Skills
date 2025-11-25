# db.dropdb

**Category**: database

## Description

Removes an existing database.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_dropdb(driver="sqlite",database,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`driver : str, required`**
   - Name of database driver
   - Used as: input, dbdriver, name
   - Allowed values: dbf, odbc, ogr, pg, sqlite

2. **`database : str, required`**
   - Name of database
   - Used as: input, dbname, name

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

db.dropdb removes an existing database using given database driver . Currently only SQLite and PostgreSQL database drivers are supported.

---

## See Also

Related tools:
- [`db.createdb`](https://grass.osgeo.org/grass-devel/manuals/db.createdb.html)
- [`db.describe`](https://grass.osgeo.org/grass-devel/manuals/db.describe.html)
- [`db.droptable`](https://grass.osgeo.org/grass-devel/manuals/db.droptable.html)
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`db.login`](https://grass.osgeo.org/grass-devel/manuals/db.login.html)
- [`db.tables`](https://grass.osgeo.org/grass-devel/manuals/db.tables.html)

---

## Authors

Radim Blazek, ITC-Irst, Trento, Italy SQLite and PostgreSQL support by Martin Landa, Czech Technical
University in Prague, Czech Republic

---

## Resources

- [Official db.dropdb manual](https://grass.osgeo.org/grass-devel/manuals/db.dropdb.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.dropdb.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
