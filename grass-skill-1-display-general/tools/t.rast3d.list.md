# t.rast3d.list

**Category**: temporal

## Description

Lists registered maps of a space time raster3d dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast3d_list(input,order="start_time",columns="name,mapset,start_time,end_time",where=None,method="cols",separator="pipe",output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster3d dataset
   - Used as: input, str3ds, name

2. **`order : str | list[str], optional`**
   - Order the space time dataset by category
   - Allowed values: id, name, creator, mapset, temporal_type, creation_time, start_time, end_time, north, south, west, east, nsres, tbres, ewres, cols, rows, depths, number_of_cells, min, max
   - Default: start_time

3. **`columns : str | list[str], optional`**
   - Columns to be printed to stdout
   - Allowed values: id, name, creator, mapset, temporal_type, creation_time, start_time, end_time, north, south, west, east, nsres, tbres, ewres, cols, rows, depths, number_of_cells, min, max
   - Default: name,mapset,start_time,end_time

4. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

5. **`method : str, optional`**
   - Method used for data listing
   - Allowed values: cols, comma, delta, deltagaps, gran
   - Default: cols

6. **`separator : str, optional`**
   - Field separator character between the output columns
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

7. **`output : str, optional`**
   - Name for output file
   - Used as: output, file, name

8. **`flags : str, optional`**
   - Allowed values: s
   - s
   - Suppress printing of column names

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


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.list.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast3d.list provides the same functionality as t.rast.list , the only difference is the 3D raster map
layer metadata. Please refer to the manual page of t.rast.list .

---

## See Also

Related tools:
- [`t.rast.list`](https://grass.osgeo.org/grass-devel/manuals/t.rast.list.html)
- [`g.list`](https://grass.osgeo.org/grass-devel/manuals/g.list.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`t.list`](https://grass.osgeo.org/grass-devel/manuals/t.list.html)
- [`t.vect.list`](https://grass.osgeo.org/grass-devel/manuals/t.vect.list.html)

---

## Resources

- [Official t.rast3d.list manual](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.list.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.list.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
