# v.to.db

**Category**: vector

## Description

Populates attribute values from vector features.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_to_db(map,layer="1",type="point,line,boundary,centroid",option,columns,units=None,query_layer="1",query_column=None,separator="pipe",format="plain",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name (write to)
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`type : str | list[str], optional`**
   - Feature type
   - For coor valid point/centroid, for length valid line/boundary
   - Allowed values: point, line, boundary, centroid

4. **`option : str, required`**
   - Value to upload
   - Allowed values: cat, area, compact, fd, perimeter, length, count, coor, start, end, sides, query, slope, sinuous, azimuth, bbox
   - cat: insert new row for each category if doesn't exist yet
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.to.db.html#__tabbed_2_3) for all details)*

5. **`columns : str | list[str], required`**
   - Name of attribute column(s) to populate
   - Name of attribute column(s)
   - Used as: input, dbcolumn, name

6. **`units : str, optional`**
   - Units
   - Allowed values: miles, feet, meters, kilometers, acres, hectares, radians, degrees

7. **`query_layer : str, optional`**
   - Query layer number or name (read from)
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

8. **`query_column : str, optional`**
   - Name of attribute column used for 'query' option
   - E.g. 'cat', 'count(*)', 'sum(val)'
   - Used as: input, dbcolumn, name

9. **`separator : str, optional`**
   - Field separator for print mode
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

10. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.to.db.html#__tabbed_2_3) for all details)*

11. **`flags : str, optional`**
   - Allowed values: p, h, s, c
   - p
   - Print only
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.to.db.html#__tabbed_2_3) for all details)*

12. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

13. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

14. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

15. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.to.db.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.to.db loads vector map features or metrics into a database table, or
prints them (or the SQL queries used to obtain them) in a form of a
human-readable report. For uploaded/printed category values '-1' is used
for 'no category' and 'null'/'-' if category cannot be found or multiple
categories were found. For line azimuths '-1' is used for closed lines
(start equals end).

---

## See Also

Related tools:
- [`d.what.vect`](https://grass.osgeo.org/grass-devel/manuals/d.what.vect.html)
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`v.category`](https://grass.osgeo.org/grass-devel/manuals/v.category.html)
- [`v.db.addtable`](https://grass.osgeo.org/grass-devel/manuals/v.db.addtable.html)
- [`v.db.addcolumn`](https://grass.osgeo.org/grass-devel/manuals/v.db.addcolumn.html)
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [`v.distance`](https://grass.osgeo.org/grass-devel/manuals/v.distance.html)
- [`v.report`](https://grass.osgeo.org/grass-devel/manuals/v.report.html)
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)
- [`v.what`](https://grass.osgeo.org/grass-devel/manuals/v.what.html)

---

## Authors

Radim Blazek, ITC-irst, Trento, Italy Line sinuosity implemented by Wolf Bergenheim

---

## Resources

- [Official v.to.db manual](https://grass.osgeo.org/grass-devel/manuals/v.to.db.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.to.db.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
