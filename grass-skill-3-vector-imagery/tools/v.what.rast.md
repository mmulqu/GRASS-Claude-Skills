# v.what.rast

**Category**: vector

## Description

Uploads raster values at positions of vector points to the table.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_what_rast(map,layer="1",type="point",raster,column=None,where=None,separator="comma",format="plain",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector points map for which to edit attributes
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, centroid
   - Default: point

4. **`raster : str | np.ndarray, required`**
   - Name of existing raster map to be queried
   - Used as: input, raster, name

5. **`column : str, optional`**
   - Name of attribute column to be updated with the query result
   - Used as: input, dbcolumn, name

6. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

7. **`separator : str, optional`**
   - Field separator for CSV style output
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

8. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, csv, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html#__tabbed_2_3) for all details)*

9. **`flags : str, optional`**
   - Allowed values: i, p
   - i
   - Interpolate values from the nearest four cells
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html#__tabbed_2_3) for all details)*

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.what.rast retrieves raster value from a given raster map for each
point or centroid stored in a given vector map. It can update a column in the linked vector attribute table with the retrieved
raster cell value or print it.

The column type needs to be numeric (integer, float, double, ...). If
the column doesn't exist in the vector attribute table than the module
will create the new column of type corresponding with the input raster
map.

If the -p flag is used, then the attribute table is not updated and
the results are printed to standard output.

If the -i flag is used, then the value to be uploaded to the
database is interpolated from the four nearest raster cells values using
an inverse distance weighting method (IDW). This is useful for cases
when the vector point density is much higher than the raster cell size.

---

## See Also

Related tools:
- [`v.category`](https://grass.osgeo.org/grass-devel/manuals/v.category.html)
- [`v.db.addtable`](https://grass.osgeo.org/grass-devel/manuals/v.db.addtable.html)
- [`v.db.select`](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html)
- [`v.drape`](https://grass.osgeo.org/grass-devel/manuals/v.drape.html)
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)
- [`v.rast.stats`](https://grass.osgeo.org/grass-devel/manuals/v.rast.stats.html)
- [`v.what.vect`](https://grass.osgeo.org/grass-devel/manuals/v.what.vect.html)

---

## Authors

Radim Blazek Hamish Bowman (interpolation)

---

## Resources

- [Official v.what.rast manual](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
