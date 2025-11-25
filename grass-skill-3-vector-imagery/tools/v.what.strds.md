# v.what.strds

**Category**: vector

## Description

Uploads space time raster dataset values at positions of vector points to the table.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_what_strds(input,strds,output=None,where=None,t_where=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`strds : str | list[str], required`**
   - Name of the input space time raster datasets
   - Used as: input, strds, name

3. **`output : str, optional`**
   - Name for output vector map
   - Used as: output, vector, name

4. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

5. **`t_where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

6. **`flags : str, optional`**
   - Allowed values: u
   - u
   - Update attribute table of input vector map

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

v.what.strds retrieves raster values from a given space-time raster
datasets (STRDS) using a point vector map.

---

## See Also

Related tools:
- [`v.what.rast`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html)
- [`t.vect.observe.strds`](https://grass.osgeo.org/grass-devel/manuals/t.vect.observe.strds.html)

---

## Resources

- [Official v.what.strds manual](https://grass.osgeo.org/grass-devel/manuals/v.what.strds.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.what.strds.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
