# v.rast.stats

**Category**: vector

## Description

Calculates univariate statistics from a raster map based on a vector map and uploads statistics to new attribute columns.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_rast_stats(map,layer="1",type="point,line,boundary,centroid,area",where=None,raster,column_prefix,method="number,null_cells,minimum,maximum,range,average,stddev,variance,coeff_var,sum,first_quartile,median,third_quartile,percentile",percentile=90,flags=None,verbose=None,quiet=None,superquiet=None)
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
   - Default: point,line,boundary,centroid,area

4. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

5. **`raster : str | list[str], required`**
   - Name of input raster map to calculate statistics from
   - Used as: input, raster, name

6. **`column_prefix : str | list[str], required`**
   - Column prefix for new attribute columns

7. **`method : str | list[str], optional`**
   - The methods to use
   - Allowed values: number, null_cells, minimum, maximum, range, average, stddev, variance, coeff_var, sum, first_quartile, median, third_quartile, percentile
   - Default: number,null_cells,minimum,maximum,range,average,stddev,variance,coeff_var,sum,first_quartile,median,third_quartile,percentile

8. **`percentile : int, optional`**
   - Percentile to calculate
   - Allowed values: 0-100
   - Default: 90

9. **`flags : str, optional`**
   - Allowed values: c, d
   - c
   - Continue if upload column(s) already exist
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.rast.stats.html#__tabbed_2_3) for all details)*

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.rast.stats.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.rast.stats calculates basic univariate statistics from a raster map
only for the parts covered by the specified vector map. The vector map
will be rasterized according to the raster map resolution. Then
univariate statistics are calculated per vector category (cat) from the
raster map and the results uploaded to the vector map attribute table. A
new column is generated in the attribute table for each statistic
requested in method (if not already present).

The univariate statistics include the number of raster cells counted,
the number of raster NULL cells counted, minimum and maximum cell
values, range, average, standard deviation, variance, coefficient of
variation, sum, first quartile, median, third quartile, and percentile.

---

## See Also

Related tools:
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)
- [`v.vect.stats`](https://grass.osgeo.org/grass-devel/manuals/v.vect.stats.html)
- [`v.what.rast`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html)
- [`v.what.rast3`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast3.html)
- [`v.what.vect`](https://grass.osgeo.org/grass-devel/manuals/v.what.vect.html)

---

## Resources

- [Official v.rast.stats manual](https://grass.osgeo.org/grass-devel/manuals/v.rast.stats.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.rast.stats.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
