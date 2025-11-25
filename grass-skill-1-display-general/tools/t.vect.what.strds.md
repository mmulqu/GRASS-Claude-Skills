# t.vect.what.strds

**Category**: temporal

## Description

Stores raster map values at spatial and temporal positions of vector points as vector attributes.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_vect_what_strds(input,strds,column=None,method="disabled",where=None,t_where=None,sampling="start",verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time vector dataset
   - Used as: input, stvds, name

2. **`strds : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

3. **`column : str, optional`**
   - Name of the vector column to be created and to store sampled raster values
   - The use of a column name forces t.vect.what.rast to sample only values from the first map found in an interval. Otherwise the raster map names are used as column names

4. **`method : str, required`**
   - Aggregate operation to be performed on the raster maps
   - Allowed values: disabled, average, count, median, mode, minimum, min_raster, maximum, max_raster, stddev, range, sum, variance, diversity, slope, offset, detcoeff, quart1, quart3, perc90, quantile, skewness, kurtosis
   - Default: disabled

5. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

6. **`t_where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

7. **`sampling : str | list[str], optional`**
   - The method to be used for sampling the input dataset
   - Used as: name
   - Allowed values: start, during, overlap, contain, equal, follows, precedes

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

The module t.vect.what.strds samples a space time raster dataset
(STRDS) at the spatio-temporal locations of a space time vector dataset
(STVDS).

---

## See Also

Related tools:
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)
- [`v.what.rast`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html)
- [`v.what.rast3`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast3.html)
- [`v.what.strds`](https://grass.osgeo.org/grass-devel/manuals/v.what.strds.html)
- [`v.what.vect`](https://grass.osgeo.org/grass-devel/manuals/v.what.vect.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.vect.what.strds manual](https://grass.osgeo.org/grass-devel/manuals/t.vect.what.strds.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.vect.what.strds.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
