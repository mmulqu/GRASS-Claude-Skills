# v.db.reconnect.all

**Category**: vector

## Description

Reconnects attribute tables for all vector maps from the current mapset to a new database.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_db_reconnect_all(old_database=None,old_schema=None,new_driver=None,new_database=None,new_schema=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`old_database : str, optional`**
   - Name of source database
   - Used as: input, dbname, name

2. **`old_schema : str, optional`**
   - Name of source database schema
   - Do not use this option if schemas are not supported by driver/database server
   - Used as: name

3. **`new_driver : str, optional`**
   - Name for target driver

4. **`new_database : str, optional`**
   - Name for target database
   - Used as: input, dbname, name

5. **`new_schema : str, optional`**
   - Name for target database schema
   - Do not use this option if schemas are not supported by driver/database server
   - Used as: name

6. **`flags : str, optional`**
   - Allowed values: c, d
   - c
   - Copy attribute tables to the target database if not exist
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.db.reconnect.all.html#__tabbed_2_3) for all details)*

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

v.db.reconnect.all changes database connection of all layers of all
vector maps in the current mapset from the source ( old_database ) to
the target ( new_database ) database. If a link does not match the old_database it is left untouched.

If no new database is given, the default datase of the mapset is used as
printed by db.connect -g . If no old database is given, all layers
without a link in the new database will be liniked to the new database.
If an old database is given, only links in the old database will be
changed.

Optionally attribute tables in new_database can be created if not
exist by -c flag. In this case v.db.reconnect.all also tries to
create an index on key column (usually "cat" column).

---

## See Also

Related tools:
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [`db.connect`](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [`db.copy`](https://grass.osgeo.org/grass-devel/manuals/db.copy.html)
- [`db.createdb`](https://grass.osgeo.org/grass-devel/manuals/db.createdb.html)
- [`db.droptable`](https://grass.osgeo.org/grass-devel/manuals/db.droptable.html)

---

## Authors

Radim Blazek Major update by Martin Landa, Czech Technical University in Prague,
Czech Republic

---

## Resources

- [Official v.db.reconnect.all manual](https://grass.osgeo.org/grass-devel/manuals/v.db.reconnect.all.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.db.reconnect.all.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
