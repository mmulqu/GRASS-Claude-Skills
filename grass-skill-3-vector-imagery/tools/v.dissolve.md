# v.dissolve

**Category**: vector

## Description

Dissolves adjacent or overlapping features sharing a common category number or attribute.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_dissolve(input,layer="1",column=None,output,aggregate_columns=None,aggregate_methods=None,result_columns=None,aggregate_backend=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name.
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`column : str, optional`**
   - Name of attribute column used to dissolve features
   - Used as: input, dbcolumn, name

4. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

5. **`aggregate_columns : str | list[str], optional`**
   - Names of attribute columns to get aggregate statistics for
   - One column name or SQL expression per method if result columns are specified
   - Used as: input, dbcolumn, name

6. **`aggregate_methods : str | list[str], optional`**
   - Aggregate statistics method (e.g., sum)
   - Default is all available basic statistics for a given backend (for sql backend: avg, count, max, min, sum)

7. **`result_columns : str | list[str], optional`**
   - New attribute column names for aggregate statistics results
   - Defaults to aggregate column name and statistics name and can contain type
   - Used as: input, dbcolumn, name

8. **`aggregate_backend : str, optional`**
   - Backend for attribute aggregation
   - Default is sql unless the provided aggregate methods are for univar
   - Allowed values: sql, univar
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.dissolve.html#__tabbed_2_3) for all details)*

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.dissolve.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The v.dissolve module is used to merge adjacent or overlapping
features in a vector map that share the same category value. The
resulting merged feature(s) retain this category value.

Figure: Areas with the same attribute value (first image) are merged
into one (second image).

Instead of dissolving features based on the category values, the user
can define an integer or string column using the column parameter.
In that case, features that share the same value in that column are
dissolved. Note, the newly created layer does not retain the category
(cat) values from the input layer.

Note that multiple areas with the same category or the same attribute
value that are not adjacent are merged into one entity, which consists
of multiple features, i.e., a multipart feature.

The attributes of merged areas can be aggregated using various
aggregation methods. The specific methods available depend on the
backend used for aggregation. Two aggregate backends (specified with the aggregate_backend parameter) are available, univar and sql . The
backend is determined automatically based on the requested methods. When
the function is one of the SQL build-in aggregate functions, the sql backend is used. Otherwise, the univar backend is used.

The default behavior is intended for interactive use and testing. For
scripting and other automated usage, explicitly specifying the backend
with the aggregate_backend parameter is strongly recommended. When
choosing, note that the sql aggregate backend, regardless of the
underlying database, will typically perform significantly better than
the univar backend.

When univar is used, the methods available are the ones which v.db.univar uses by default, i.e., n , min , max , range , mean , mean_abs , variance , stddev , coef_var , and sum .

When the sql backend is used, the methods depend on the SQL database
backend used for the attribute table of the input vector. For SQLite,
there are at least the following built-in aggregate
functions : count , min , max , avg , sum , and total . For PostgreSQL, the list of aggregate
functions is much longer and includes, e.g., count , min , max , avg , sum , stddev , and variance .

If only the parameter aggregate_columns is provided, all the
following aggregation statistics are calculated: n , min , max , mean , and sum . If the univar backend is specified, all the
available methods for the univar backend are used.

The aggregate_methods parameter can be used to specify which
aggregation statistics should be computed. Alternatively, the parameter aggregate_columns can be used to specify the method using SQL
syntax. This provides the highest flexibility, and it is suitable for
scripting. The SQL statement should specify both the column and the
functions applied, e.g.,

Note that when the aggregate_columns parameter is used, the sql backend should be used. In addition, the aggregate_columns and aggregate_methods cannot be used together.

For convenience, certain methods, namely n , count , mean , and avg , are automatically converted to the appropriate name for the
selected backend. However, for scripting, it is recommended to specify
the appropriate method (function) name for the backend, as the
conversion is a heuristic that may change in the future.

If the result_columns is not provided, each method is applied to
each column specified by aggregate_columns . This results in a column
for each of the combinations. These result columns have auto-generated
names based on the aggregate column and method. For example, setting the
following parameters:

results in the following columns: A_sum, A_n, B_sum, B_n. See the
Examples section.

If the result_column is provided, each method is applied only once
to the matching column in the aggregate column list, and the result will
be available under the name of the matching result column. For example,
setting the following parameter:

results in the column sum_a with the sum of the values of A and the
column n_b with the max of B . Note that the number of items in aggregate_columns , aggregate_methods (unless omitted), and result_column needs to match, and no combinations are created on the
fly. See the Examples section.

For scripting, it is recommended to specify all resulting column names,
while for interactive use, automatically created combinations are
expected to be beneficial, especially for exploratory analysis.

The type of the result column is determined based on the method
selected. For n and count , the type is INTEGER and for all other
methods, it is DOUBLE. Aggregate methods that produce other types
require the type to be specified as part of the result_columns . A
type can be provided in result_columns using the SQL syntax name type , e.g., sum_of_values double precision . Type specification
is mandatory when SQL syntax is used in aggregate_columns (and aggregate_methods is omitted).

---

## See Also

Related tools:
- [`v.category`](https://grass.osgeo.org/grass-devel/manuals/v.category.html)
- [`v.centroids`](https://grass.osgeo.org/grass-devel/manuals/v.centroids.html)
- [`v.extract`](https://grass.osgeo.org/grass-devel/manuals/v.extract.html)
- [`v.reclass`](https://grass.osgeo.org/grass-devel/manuals/v.reclass.html)
- [`v.db.univar`](https://grass.osgeo.org/grass-devel/manuals/v.db.univar.html)
- [`v.db.select`](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html)

---

## Authors

M. Hamish Bowman, Department of Marine Science, Otago University, New
Zealand (module) Markus Neteler (column support) Trevor Wiens (help page) Vaclav Petras, NC State University, Center for Geospatial Analytics,
GeoForAll Lab (aggregate statistics)

---

## Resources

- [Official v.dissolve manual](https://grass.osgeo.org/grass-devel/manuals/v.dissolve.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.dissolve.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
