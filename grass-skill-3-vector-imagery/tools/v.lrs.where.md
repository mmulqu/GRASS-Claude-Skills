# v.lrs.where

**Category**: vector

## Description

Finds line id and real km+offset for given points in vector map using linear reference system.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_lrs_where(lines,points,llayer="1",player="1",rsdriver="sqlite",rsdatabase="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",rstable,threshold=1000,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`lines : str, required`**
   - Name of input vector map
   - Input vector map containing lines
   - Used as: input, vector, name

2. **`points : str, required`**
   - Name of input vector map
   - Input vector map containing points
   - Used as: input, vector, name

3. **`llayer : str, optional`**
   - Layer number or name
   - Line layer
   - Used as: input, layer

4. **`player : str, optional`**
   - Layer number or name
   - Point layer
   - Used as: input, layer

5. **`rsdriver : str, optional`**
   - Driver name for reference system table
   - Allowed values: dbf, odbc, ogr, pg, sqlite
   - Default: sqlite

6. **`rsdatabase : str, optional`**
   - Database name for reference system table
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db

7. **`rstable : str, required`**
   - Name of the reference system table

8. **`threshold : float, optional`**
   - Maximum distance to nearest line
   - Default: 1000

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.lrs.where.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.lrs.where identifies line id and real milepost+offset for points in
vector map using linear reference system.

---

## See Also

Related tools:
- [`v.lrs.where`](https://grass.osgeo.org/grass-devel/manuals/v.lrs.where.html)
- [`v.lrs.segment`](https://grass.osgeo.org/grass-devel/manuals/v.lrs.segment.html)
- [`v.lrs.label`](https://grass.osgeo.org/grass-devel/manuals/v.lrs.label.html)

---

## Authors

Radim Blazek, ITC-irst/MPA Solutions Documentation update (based on above journal article and available
fragments): Markus Neteler

---

## Resources

- [Official v.lrs.where manual](https://grass.osgeo.org/grass-devel/manuals/v.lrs.where.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.lrs.where.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
