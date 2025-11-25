# v.lrs.segment

**Category**: vector

## Description

Creates points/segments from input lines, linear reference system and positions read from stdin or a file.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_lrs_segment(input,output,llayer="1",rsdriver="sqlite",rsdatabase="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",rstable,file=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Input vector map containing lines
   - Used as: input, vector, name

2. **`output : str, required`**
   - Output vector map where segments will be written
   - Used as: output, vector, name

3. **`llayer : str, optional`**
   - Layer number or name
   - Line layer
   - Used as: input, layer

4. **`rsdriver : str, optional`**
   - Driver name for reference system table
   - Allowed values: dbf, odbc, ogr, pg, sqlite
   - Default: sqlite

5. **`rsdatabase : str, optional`**
   - Database name for reference system table
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db

6. **`rstable : str, required`**
   - Name of the reference system table

7. **`file : str | io.StringIO, optional`**
   - Name of file containing segment rules. If not given, read from stdin.
   - Used as: input, file, name

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.lrs.segment.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.lrs.segment creates points/segments from input lines, linear
reference system and positions read from standard in or a file.

The format is as follows:

---

## See Also

Related tools:
- [`v.lrs.create`](https://grass.osgeo.org/grass-devel/manuals/v.lrs.create.html)
- [`v.lrs.where`](https://grass.osgeo.org/grass-devel/manuals/v.lrs.where.html)
- [`v.lrs.label`](https://grass.osgeo.org/grass-devel/manuals/v.lrs.label.html)
- [`v.segment`](https://grass.osgeo.org/grass-devel/manuals/v.segment.html)

---

## Resources

- [Official v.lrs.segment manual](https://grass.osgeo.org/grass-devel/manuals/v.lrs.segment.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.lrs.segment.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
