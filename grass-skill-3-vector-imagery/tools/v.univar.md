# v.univar

**Category**: vector

## Description

Calculates univariate statistics of vector map features. Variance and standard deviation is calculated only for points if specified.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_univar(map,layer="1",type="point,line,area",column=None,where=None,percentile=90,format="plain",flags=None,verbose=None,quiet=None,superquiet=None)
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

3. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area
   - Default: point,line,area

4. **`column : str, optional`**
   - Name of attribute column
   - Used as: input, dbcolumn, name

5. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

6. **`percentile : int, optional`**
   - Percentile to calculate (requires extended statistics flag)
   - Allowed values: 0-100
   - Default: 90

7. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, shell, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.univar.html#__tabbed_2_3) for all details)*

8. **`flags : str, optional`**
   - Allowed values: g, e, w, d
   - g
   - Print the stats in shell script style [deprecated]
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.univar.html#__tabbed_2_3) for all details)*

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.univar.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.univar calculates univariate statistics on (by default) an attribute
of, or, through the -d flag on distance between, vector map
features. Attributes are read per feature and per category value. This
means that if the map contains several features with the same category
value, the attribute is read as many times as there are features. On the
other hand, if a feature has more than one category value, each
attribute value linked to each of the category values of the feature is
read. For statistics on one attribute per category value, instead of one
attribute per feature and per category, see v.db.univar .

Extended statistics ( -e ) adds median, 1st and 3rd quartiles, and
90th percentile to the output.

---

## See Also

Related tools:
- [`db.univar`](https://grass.osgeo.org/grass-devel/manuals/db.univar.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)
- [`v.db.univar`](https://grass.osgeo.org/grass-devel/manuals/v.db.univar.html)
- [`v.distance`](https://grass.osgeo.org/grass-devel/manuals/v.distance.html)
- [`v.neighbors`](https://grass.osgeo.org/grass-devel/manuals/v.neighbors.html)
- [`v.qcount`](https://grass.osgeo.org/grass-devel/manuals/v.qcount.html)

---

## Authors

Radim Blazek, ITC-irst
extended by: Hamish Bowman, University of Otago, New Zealand Martin Landa

---

## Resources

- [Official v.univar manual](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.univar.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
