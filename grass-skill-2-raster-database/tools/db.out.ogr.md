# db.out.ogr

**Category**: database

## Description

Exports attribute tables into various formats.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_out_ogr(input,output,layer="1",format="CSV",table=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - GRASS table name
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Output table file name or DB connection string
   - Used as: output, file, name

3. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

4. **`format : str, required`**
   - Table format
   - Allowed values: CSV, DBF, GML, MySQL, PostgreSQL, SQLite
   - Default: CSV

5. **`table : str, optional`**
   - Name for output table (default: input name)
   - Used as: name

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

db.out.ogr exports GRASS attribute tables into various formats as
supported by the OGR driver on the local system (CSV, DBF, PostgreSQL,
SQLite, MySQL, ODBC, etc.).

The output parameter is used to define the output file name (if the
path is not defined, the module will attempt to write to the current
directory). In case of a database connection as output, the connection
string has to be specified.

The layer parameter is needed if the attribute table to be exported is
linked as non-default layer to a vector map.

---

## See Also

Related tools:
- [`db.tables`](https://grass.osgeo.org/grass-devel/manuals/db.tables.html)

---

## Authors

Markus Neteler Converted to Python by Glynn Clements

---

## Resources

- [Official db.out.ogr manual](https://grass.osgeo.org/grass-devel/manuals/db.out.ogr.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.out.ogr.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
