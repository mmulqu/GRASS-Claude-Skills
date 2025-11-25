# v.neighbors

**Category**: vector

## Description

Neighborhood analysis tool for vector point maps. Makes each cell value a function of the attribute values assigned to the vector points or centroids in a radius around it, and stores new cell values in an output raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_neighbors(input,layer="1",output,method="count",size,points_column=None,cats=None,where=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

4. **`method : str, required`**
   - Method for aggregate statistics (count if non given)
   - Allowed values: count, sum, average, median, mode, minimum, maximum, range, stddev, variance, diversity
   - Default: count

5. **`size : float, required`**
   - Neighborhood diameter in map units

6. **`points_column : str, optional`**
   - Column name of points map to use for statistics
   - Column of points map must be numeric
   - Used as: input, dbcolumn, name

7. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

8. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

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


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.neighbors.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

This module makes each cell value a function of the attribute values
assigned to the vector points or centroids in an area around the cell
with a diameter of size around it, and stores the new cell values in
the output raster map layer. By default, the module just counts the
number of points. The user can also choose amongst a variety of
aggregate statistics using the parameter method . These statistics are
calculated on the attributes in the point_column . Using the usual cats and where parameters the user can chose to take only a subset
of the points into account.

Note that size is defined as the diameter, and so has to be twice the
wanted search radius, and that the module works within the current
computational region which can be adjusted using g.region . If the vector map falls completely outside the
current region, the module will stop with an error.

---

## See Also

Related tools:
- [`r.neighbors`](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)
- [`v.vect.stats`](https://grass.osgeo.org/grass-devel/manuals/v.vect.stats.html)

---

## Authors

Radim Blazek, Moritz Lennert

---

## Resources

- [Official v.neighbors manual](https://grass.osgeo.org/grass-devel/manuals/v.neighbors.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.neighbors.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
