# db.droptable

**Category**: database

## Description

Drops an attribute table.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_droptable(driver=None,database=None,table,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`driver : str, optional`**
   - Name of database driver
   - If not given then default driver is used
   - Used as: input, dbdriver, name

2. **`database : str, optional`**
   - Name of database
   - If not given then default database is used
   - Used as: input, dbname, name

3. **`table : str, required`**
   - Name of table to drop
   - Used as: input, dbtable, name

4. **`flags : str, optional`**
   - Allowed values: f
   - f
   - Force removal (required for actual deletion of files)

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

db.droptable drops an attribute table. If the -f force flag is not
given then nothing is removed, instead a preview of the action to be
taken is printed.

---

## See Also

Related tools:
- [`db.dropdb`](https://grass.osgeo.org/grass-devel/manuals/db.dropdb.html)
- [`db.dropcolumn`](https://grass.osgeo.org/grass-devel/manuals/db.dropcolumn.html)
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`db.login`](https://grass.osgeo.org/grass-devel/manuals/db.login.html)
- [`db.connect`](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [`db.tables`](https://grass.osgeo.org/grass-devel/manuals/db.tables.html)
- [`db.describe`](https://grass.osgeo.org/grass-devel/manuals/db.describe.html)
- [`v.db.droptable`](https://grass.osgeo.org/grass-devel/manuals/v.db.droptable.html)

---

## Authors

Markus Neteler Driver and database options added by Martin Landa, Czech Technical
University in Prague, Czech Republic

---

## Resources

- [Official db.droptable manual](https://grass.osgeo.org/grass-devel/manuals/db.droptable.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.droptable.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
