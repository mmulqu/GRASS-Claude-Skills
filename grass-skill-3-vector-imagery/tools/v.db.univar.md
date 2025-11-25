# v.db.univar

**Category**: vector

## Description

Calculates univariate statistics on selected table column for a GRASS vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_db_univar(map,layer="1",column,where=None,percentile=90,format=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`column : str, required`**
   - Name of attribute column on which to calculate statistics (must be numeric)
   - Used as: input, dbcolumn, name

4. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

5. **`percentile : float | list[float] | str, optional`**
   - Percentile to calculate (requires extended statistics flag)
   - Allowed values: 0-100
   - Default: 90

6. **`format : str, optional`**
   - Output format
   - Allowed values: plain, json, shell
   - plain: Plain text output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.db.univar.html#__tabbed_2_3) for all details)*

7. **`flags : str, optional`**
   - Allowed values: e, g
   - e
   - Extended statistics (quartiles and 90th percentile)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.db.univar.html#__tabbed_2_3) for all details)*

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
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

v.db.univar calculates basic univariate statistics for numeric
attributes in a vector attribute table. It will calculate minimum,
maximum, range, mean, standard deviation, variance, coefficient of
variation, quartiles, median, and 90th percentile.

v.db.univar uses db.univar which in turn uses db.select to get the
attribute values on which it calculates the statistics. This means that
statistics are calculated based on the entries in the attribute table,
not based on the features in the map. One attribute value is read from
each line in the attribute table, whether there are no, one or several
features with the category value referenced by that line, or whether any
features have more than one category value. For feature-based, instead
of attribute table-based, univariate statistics on attributes see v.univar .

---

## See Also

Related tools:
- [`db.univar`](https://grass.osgeo.org/grass-devel/manuals/db.univar.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)
- [`db.select`](https://grass.osgeo.org/grass-devel/manuals/db.select.html)
- [`d.vect.thematic`](https://grass.osgeo.org/grass-devel/manuals/d.vect.thematic.html)
- [`v.random`](https://grass.osgeo.org/grass-devel/manuals/v.random.html)

---

## Authors

Michael Barton, Arizona State University
and authors of r.univar.sh (Markus Neteler et al.)

---

## Resources

- [Official v.db.univar manual](https://grass.osgeo.org/grass-devel/manuals/v.db.univar.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.db.univar.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
