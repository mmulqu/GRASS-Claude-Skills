# db.in.ogr

**Category**: database

## Description

Imports attribute tables in various formats.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_in_ogr(input,gdal_config=None,gdal_doo=None,db_table=None,output=None,key=None,encoding=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Table file to be imported or DB connection string
   - Used as: input, file, name

2. **`gdal_config : str, optional`**
   - GDAL configuration options
   - Comma-separated list of key=value pairs

3. **`gdal_doo : str, optional`**
   - GDAL dataset open options
   - Comma-separated list of key=value pairs

4. **`db_table : str, optional`**
   - Name of table from given DB to be imported
   - Used as: name

5. **`output : str, optional`**
   - Name for output table
   - Used as: output, dbtable, name

6. **`key : str, optional`**
   - Name for auto-generated unique key column

7. **`encoding : str, optional`**
   - Encoding value for attribute data

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/db.in.ogr.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

db.in.ogr imports attribute tables in various formats as supported by
the OGR library on the local system (DBF, CSV,
PostgreSQL, SQLite, MySQL, ODBC, etc.). Optionally a unique key (ID)
column can be added to the table.

---

## See Also

Related tools:
- [`db.select`](https://grass.osgeo.org/grass-devel/manuals/db.select.html)
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)
- [`v.in.db`](https://grass.osgeo.org/grass-devel/manuals/v.in.db.html)

---

## Resources

- [Official db.in.ogr manual](https://grass.osgeo.org/grass-devel/manuals/db.in.ogr.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.in.ogr.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
