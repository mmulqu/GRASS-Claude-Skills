# db.select

**Category**: database

## Description

Selects data from attribute table. Performs SQL query statement(s).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_select(sql=None,input=None,table=None,driver="sqlite",database="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",separator="pipe",vertical_separator=None,null_value=None,output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`sql : str, optional`**
   - SQL SELECT statement
   - Example: select * from towns where population > 10000
   - Used as: sql_query

2. **`input : str | io.StringIO, optional`**
   - Name of file containing SQL select statement(s)
   - '-' for standard input
   - Used as: input, file, name

3. **`table : str, optional`**
   - Name of table to query
   - Used as: input, dbtable, name

4. **`driver : str, optional`**
   - Name of database driver
   - Used as: input, dbdriver, name
   - Allowed values: dbf, odbc, ogr, pg, sqlite

5. **`database : str, optional`**
   - Name of database
   - Used as: input, dbname, name
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db

6. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

7. **`vertical_separator : str, optional`**
   - Vertical record separator (requires -v flag)
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

8. **`null_value : str, optional`**
   - String representing NULL value
   - Used as: string

9. **`output : str, optional`**
   - Name for output file (if omitted or "-" output to stdout)
   - Used as: output, file, name

10. **`flags : str, optional`**
   - Allowed values: c, d, v, t
   - c
   - Do not include column names in output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/db.select.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/db.select.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

db.select prints result of selection from database based on SQL
statement read from input file or from standard input to standard
output. Each individual query has to be written on one single line and
different queries have to be written on separate lines.

---

## Note

If parameters for database connection are already set with db.connect , they are taken as default values and do
not need to be specified each time. Output will be displayed to standard
output or can be directed to a file (option output ).

---

## See Also

Related tools:
- [`db.connect`](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [`db.describe`](https://grass.osgeo.org/grass-devel/manuals/db.describe.html)
- [`db.drivers`](https://grass.osgeo.org/grass-devel/manuals/db.drivers.html)
- [`db.droptable`](https://grass.osgeo.org/grass-devel/manuals/db.droptable.html)
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`db.login`](https://grass.osgeo.org/grass-devel/manuals/db.login.html)
- [`db.tables`](https://grass.osgeo.org/grass-devel/manuals/db.tables.html)

---

## Authors

Original author unknown (probably CERL) Modifications by Radim Blazek, ITC-Irst, Trento, Italy Support for multiple statements by Martin Landa, Czech Technical
University in Prague

---

## Resources

- [Official db.select manual](https://grass.osgeo.org/grass-devel/manuals/db.select.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.select.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
