# v.report

**Category**: vector

## Description

Reports geometry statistics for vector maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_report(map,layer="1",option,units=None,sort=None,separator="pipe",flags=None,verbose=None,quiet=None,superquiet=None)
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

3. **`option : str, required`**
   - Value to calculate
   - Allowed values: area, length, coor

4. **`units : str, optional`**
   - Units
   - Allowed values: miles, feet, meters, kilometers, acres, hectares, percent

5. **`sort : str, optional`**
   - Sort the result
   - Allowed values: asc, desc
   - asc: Sort in ascending order

6. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

7. **`flags : str, optional`**
   - Allowed values: c, d
   - c
   - Do not include column names in output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.report.html#__tabbed_2_3) for all details)*

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

v.report generates a table showing the area present in each of the
categories of a user-selected data layer.

Area is given in hectares, square meters, and square kilometers. If the
units option is used, area is given in acres, square feet, and square
miles.

Feet and acre units are always reported in their common versions (i.e.
the International Foot, exactly 5280 feet in a mile), even when the
coordinate reference system's standard map unit is the US Survey foot.

v.report works on the full map data; therefore, the current region is
ignored. If you wish to spatially limit the statistics, a map subset
must be created with v.in.region and v.overlay , and then run v.report on the new map.

---

## See Also

Related tools:
- [`v.in.region`](https://grass.osgeo.org/grass-devel/manuals/v.in.region.html)
- [`v.to.db`](https://grass.osgeo.org/grass-devel/manuals/v.to.db.html)
- [`v.overlay`](https://grass.osgeo.org/grass-devel/manuals/v.overlay.html)

---

## Resources

- [Official v.report manual](https://grass.osgeo.org/grass-devel/manuals/v.report.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.report.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
