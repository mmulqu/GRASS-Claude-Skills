# db.univar

**Category**: database

## Description

Calculates univariate statistics on selected table column.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_univar(table,column,database=None,driver=None,where=None,percentile=90,format=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`table : str, required`**
   - Name of attribute table
   - Used as: input, dbtable, name

2. **`column : str, required`**
   - Name of attribute column on which to calculate statistics (must be numeric)
   - Used as: input, dbcolumn, name

3. **`database : str, optional`**
   - Name of database
   - Used as: input, dbname, name

4. **`driver : str, optional`**
   - Name of database driver
   - Used as: input, dbdriver, name
   - Allowed values: dbf, odbc, ogr, sqlite, pg

5. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

6. **`percentile : float | list[float] | str, optional`**
   - Percentile to calculate (requires extended statistics flag)
   - Allowed values: 0-100
   - Default: 90

7. **`format : str, optional`**
   - Output format
   - Allowed values: plain, json, shell
   - plain: Plain text output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/db.univar.html#__tabbed_2_3) for all details)*

8. **`flags : str, optional`**
   - Allowed values: e, g
   - e
   - Extended statistics (quartiles and 90th percentile)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/db.univar.html#__tabbed_2_3) for all details)*

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/db.univar.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

db.univar calculates basic univariate statistics for numeric
attributes in a data table. It will calculate minimum, maximum, range,
mean, standard deviation, variance, coefficient of variation, quartiles,
median, and 90th percentile. It uses db.select to create list values
for statistical calculations. NOTES If the database and driver are not
specified, the default values set in db.connect will be used.

---

## See Also

Related tools:
- [`v.db.univar`](https://grass.osgeo.org/grass-devel/manuals/v.db.univar.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)
- [`db.select`](https://grass.osgeo.org/grass-devel/manuals/db.select.html)
- [`d.vect.thematic`](https://grass.osgeo.org/grass-devel/manuals/d.vect.thematic.html)

---

## Authors

Michael Barton, Arizona State University
and authors of r.univar.sh

---

## Resources

- [Official db.univar manual](https://grass.osgeo.org/grass-devel/manuals/db.univar.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.univar.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
