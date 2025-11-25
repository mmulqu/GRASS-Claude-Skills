# v.db.connect

**Category**: vector

## Description

Prints/sets DB connection for a vector map to attribute table.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_db_connect(map,driver="sqlite",database="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",table=None,key="cat",layer="1",separator=None,format=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`driver : str, optional`**
   - Name of database driver
   - Used as: input, dbdriver, name
   - Allowed values: dbf, odbc, ogr, pg, sqlite

3. **`database : str, optional`**
   - Name of database
   - Used as: input, dbname, name
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db

4. **`table : str, optional`**
   - Name of attribute table
   - Used as: input, dbtable, name

5. **`key : str, optional`**
   - Name of key column
   - Must refer to an integer column
   - Used as: name

6. **`layer : str, optional`**
   - Layer number or name
   - Format: layer number[/layer name]
   - Used as: output, layer

7. **`separator : str, optional`**
   - Field separator for printing output
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

8. **`format : str, optional`**
   - Output format
   - Used as: name
   - Allowed values: plain, csv, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html#__tabbed_2_3) for all details)*

9. **`flags : str, optional`**
   - Allowed values: p, g, c, d
   - p
   - Print all map connection parameters and exit
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html#__tabbed_2_3) for all details)*

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.db.connect prints or sets database connection for a vector map. The
user can add or remove link to attribute table on the certain layer.

---

## Note

Connection information (driver, database, table, key) is stored for each
map, in the file

If parameters for database connection are already set with db.connect , they are taken as default values and do not
need to be specified each time.

When printing database connection ( p or g flag) the parameter layer is ignored, i.e. all connections are printed to the output.

Attention: Removing a vector map will also delete all tables linked
to it! If you use v.db.connect to link further tables
to your map, it is advisable to make a copy from those tables first and
connect the copied tables to the vector map (see also v.overlay ).

The -g flag is deprecated and will be removed in a future release. Please
use format=csv option with the -p flag instead.

---

## See Also

Related tools:
- [`db.connect`](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [`db.copy`](https://grass.osgeo.org/grass-devel/manuals/db.copy.html)
- [`db.tables`](https://grass.osgeo.org/grass-devel/manuals/db.tables.html)
- [`v.db.addtable`](https://grass.osgeo.org/grass-devel/manuals/v.db.addtable.html)
- [`v.db.droptable`](https://grass.osgeo.org/grass-devel/manuals/v.db.droptable.html)
- [`v.db.addcolumn`](https://grass.osgeo.org/grass-devel/manuals/v.db.addcolumn.html)
- [`v.db.dropcolumn`](https://grass.osgeo.org/grass-devel/manuals/v.db.dropcolumn.html)
- [`v.external`](https://grass.osgeo.org/grass-devel/manuals/v.external.html)
- [`v.in.db`](https://grass.osgeo.org/grass-devel/manuals/v.in.db.html)
- [`v.overlay`](https://grass.osgeo.org/grass-devel/manuals/v.overlay.html)

---

## Resources

- [Official v.db.connect manual](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
