# v.vect.stats

**Category**: vector

## Description

Count points in areas, calculate statistics from point attributes.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_vect_stats(points,areas,type="point",points_layer="1",points_cats=None,points_where=None,areas_layer="1",areas_cats=None,areas_where=None,method=None,points_column=None,count_column=None,stats_column=None,separator=None,format="plain",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`points : str, required`**
   - Name of existing vector map with points
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`areas : str, required`**
   - Name of existing vector map with areas
   - Or data source for direct OGR access
   - Used as: input, vector, name

3. **`type : str | list[str], optional`**
   - Feature type
   - Input feature type
   - Allowed values: point, centroid

4. **`points_layer : str, optional`**
   - Layer number for points map
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

5. **`points_cats : str, optional`**
   - Category values for points map
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

6. **`points_where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword for points map
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

7. **`areas_layer : str, optional`**
   - Layer number for area map
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

8. **`areas_cats : str, optional`**
   - Category values for area map
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

9. **`areas_where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword for area map
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

10. **`method : str, optional`**
   - Method for aggregate statistics
   - Allowed values: sum, average, median, mode, minimum, min_cat, maximum, max_cat, range, stddev, variance, diversity

11. **`points_column : str, optional`**
   - Column name of points map to use for statistics
   - Column of points map must be numeric
   - Used as: input, dbcolumn, name

12. **`count_column : str, optional`**
   - Column name to upload points count
   - Column to hold points count, must be of type integer, will be created if not existing
   - Used as: input, dbcolumn, name

13. **`stats_column : str, optional`**
   - Column name to upload statistics
   - Column to hold statistics, must be of type double, will be created if not existing
   - Used as: input, dbcolumn, name

14. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

15. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, csv, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.vect.stats.html#__tabbed_2_3) for all details)*

16. **`flags : str, optional`**
   - Allowed values: p
   - p
   - Print output to stdout, do not update attribute table

17. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

18. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

19. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 19 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.vect.stats.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.vect.stats counts the number of points in vector map points falling into each area in vector map areas . Optionally statistics on
point attributes in points are calculated for each area. The results
are either uploaded to the attribute table of the vector map areas or
printed to stdout.

Using numeric attribute values of all points falling into a given area,
a new value is determined with the selected method. v.vect.stats can
perform the following operations:

sum The sum of values.

average The average value of all point attributes (sum / count).

median The value found half-way through a list of the attribute values, when
these are ranged in numerical order.

mode The most frequently occurring value.

minimum The minimum observed value.

min_cat The point category corresponding to the minimum observed value.

maximum The maximum observed value.

max_cat The point category corresponding to the maximum observed value.

range The range of the observed values.

stddev The statistical standard deviation of the attribute values.

variance The statistical variance of the attribute values.

diversity The number of different attribute values.

---

## Resources

- [Official v.vect.stats manual](https://grass.osgeo.org/grass-devel/manuals/v.vect.stats.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.vect.stats.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
