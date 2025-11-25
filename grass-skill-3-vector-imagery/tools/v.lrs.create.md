# v.lrs.create

**Category**: vector

## Description

Creates a linear reference system.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_lrs_create(in_lines,out_lines,err=None,points,llayer="1",player="1",lidcol,pidcol,start_mp="start_mp",start_off="start_off",end_mp="end_mp",end_off="end_off",rsdriver="sqlite",rsdatabase="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",rstable,threshold=1,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`in_lines : str, required`**
   - Name of input vector map
   - Input vector map containing lines
   - Used as: input, vector, name

2. **`out_lines : str, required`**
   - Output vector map where oriented lines are written
   - Used as: output, vector, name

3. **`err : str, optional`**
   - Output vector map of errors
   - Used as: output, vector, name

4. **`points : str, required`**
   - Name of input vector map
   - Input vector map containing reference points
   - Used as: input, vector, name

5. **`llayer : str, optional`**
   - Layer number or name
   - Line layer
   - Used as: input, layer

6. **`player : str, optional`**
   - Layer number or name
   - Point layer
   - Used as: input, layer

7. **`lidcol : str, required`**
   - Column containing line identifiers for lines

8. **`pidcol : str, required`**
   - Column containing line identifiers for points

9. **`start_mp : str, optional`**
   - Column containing milepost position for the beginning of next segment
   - Default: start_mp

10. **`start_off : str, optional`**
   - Column containing offset from milepost for the beginning of next segment
   - Default: start_off

11. **`end_mp : str, optional`**
   - Column containing milepost position for the end of previous segment
   - Default: end_mp

12. **`end_off : str, optional`**
   - Column containing offset from milepost for the end of previous segment
   - Default: end_off

13. **`rsdriver : str, optional`**
   - Driver name for reference system table
   - Allowed values: dbf, odbc, ogr, pg, sqlite
   - Default: sqlite

14. **`rsdatabase : str, optional`**
   - Database name for reference system table
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db

15. **`rstable : str, required`**
   - Name of table where the reference system will be written
   - New table is created by this module

16. **`threshold : float, optional`**
   - Maximum distance of point to line allowed
   - Default: 1

17. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

18. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

19. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

20. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 20 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.lrs.create.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.lrs.create generates a LRS (Linear Reference System) from vector
line and point data.

It is highly recommended to work with polylines instead of segmented
vector lines. The command v.build.polylines creates this map
structure.

---

## See Also

Related tools:
- [`v.build.polylines`](https://grass.osgeo.org/grass-devel/manuals/v.build.polylines.html)
- [`v.lrs.segment`](https://grass.osgeo.org/grass-devel/manuals/v.lrs.segment.html)
- [`v.lrs.where`](https://grass.osgeo.org/grass-devel/manuals/v.lrs.where.html)
- [`v.lrs.label`](https://grass.osgeo.org/grass-devel/manuals/v.lrs.label.html)

---

## Authors

Radim Blazek, ITC-irst/MPA Solutions Documentation update (based on above journal article and available
fragments): Markus Neteler

---

## Resources

- [Official v.lrs.create manual](https://grass.osgeo.org/grass-devel/manuals/v.lrs.create.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.lrs.create.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
