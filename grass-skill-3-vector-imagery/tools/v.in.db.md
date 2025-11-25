# v.in.db

**Category**: vector

## Description

Creates new vector (points) map from database table containing coordinates.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_in_db(table,driver="sqlite",database="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",x,y,z=None,key=None,where=None,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`table : str, required`**
   - Input table name
   - Used as: input, dbtable, name

2. **`driver : str, optional`**
   - Name of database driver
   - Used as: input, dbdriver, name
   - Allowed values: dbf, odbc, ogr, pg, sqlite

3. **`database : str, optional`**
   - Name of database
   - Used as: input, dbname, name
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db

4. **`x : str, required`**
   - Name of column containing x coordinate
   - Used as: input, dbcolumn, name

5. **`y : str, required`**
   - Name of column containing y coordinate
   - Used as: input, dbcolumn, name

6. **`z : str, optional`**
   - Name of column containing z coordinate
   - Used as: input, dbcolumn, name

7. **`key : str, optional`**
   - Name of column containing category number
   - Must refer to an integer column
   - Used as: input, dbcolumn, name

8. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

9. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

10. **`flags : str, optional`**
   - Allowed values: t
   - t
   - Use imported table as attribute table for new map

11. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

12. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

13. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

14. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.in.db.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.in.db creates a new vector point map from database table or file
containing coordinates.

---

## See Also

Related tools:
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`db.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/db.in.ogr.html)
- [`v.info`](https://grass.osgeo.org/grass-devel/manuals/v.info.html)
- [`v.in.geonames`](https://grass.osgeo.org/grass-devel/manuals/v.in.geonames.html)
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)
- [`v.to.db`](https://grass.osgeo.org/grass-devel/manuals/v.to.db.html)

---

## Authors

Radim Blazek Various updates for GRASS 7 by Martin Landa, Czech Technical University
in Prague, Czech Republic

---

## Resources

- [Official v.in.db manual](https://grass.osgeo.org/grass-devel/manuals/v.in.db.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.in.db.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
