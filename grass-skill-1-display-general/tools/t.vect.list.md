# t.vect.list

**Category**: temporal

## Description

Lists registered maps of a space time vector dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_vect_list(input,order="start_time",columns="name,layer,mapset,start_time,end_time",where=None,method="cols",separator="pipe",output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time vector dataset
   - Used as: input, stvds, name

2. **`order : str | list[str], optional`**
   - Sort the space time dataset by category
   - Allowed values: id, name, layer, creator, mapset, temporal_type, creation_time, start_time, end_time, north, south, west, east, points, lines, boundaries, centroids, faces, kernels, primitives, nodes, areas, islands, holes, volumes
   - Default: start_time

3. **`columns : str | list[str], optional`**
   - Columns to be printed to stdout
   - Allowed values: id, name, layer, creator, mapset, temporal_type, creation_time, start_time, end_time, north, south, west, east, points, lines, boundaries, centroids, faces, kernels, primitives, nodes, areas, islands, holes, volumes
   - Default: name,layer,mapset,start_time,end_time

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
   - Allowed values: u
   - u
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


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.vect.list.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The t.vect.list module provides the same functionality as t.rast.list , the only difference is the vector map
layer metadata.

---

## See Also

Related tools:
- [`g.list`](https://grass.osgeo.org/grass-devel/manuals/g.list.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`t.list`](https://grass.osgeo.org/grass-devel/manuals/t.list.html)
- [`t.rast.list`](https://grass.osgeo.org/grass-devel/manuals/t.rast.list.html)
- [`t.rast3d.list`](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.list.html)

---

## Resources

- [Official t.vect.list manual](https://grass.osgeo.org/grass-devel/manuals/t.vect.list.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.vect.list.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
