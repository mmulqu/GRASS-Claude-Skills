# t.list

**Category**: temporal

## Description

Lists space time datasets and maps registered in the temporal database.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_list(type="strds",temporaltype="absolute,relative",order="id",columns="id",where=None,separator="pipe",output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`type : str, optional`**
   - Type of the space time dataset or map, default is strds
   - Allowed values: strds,  str3ds,  stvds,  raster,  raster_3d,  vector

2. **`Default: strds`**

3. **`temporaltype : str | list[str], optional`**
   - The temporal type of the space time dataset
   - Used as: name
   - Allowed values: absolute, relative

4. **`order : str | list[str], optional`**
   - Sort the space time dataset by category
   - Columns number_of_maps and granularity only available for space time datasets
   - Allowed values: id, name, semantic_label, creator, mapset, number_of_maps, creation_time, start_time, end_time, interval, north, south, west, east, granularity

5. **`columns : str | list[str], optional`**
   - Columns to be printed to stdout
   - Columns number_of_maps and granularity only available for space time datasets
   - Allowed values: id, name, semantic_label, creator, mapset, number_of_maps, creation_time, start_time, end_time, north, south, west, east, granularity, all

6. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

7. **`separator : str, optional`**
   - Field separator character between the output columns
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

8. **`output : str, optional`**
   - Name for output file
   - Used as: output, file, name

9. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Print the column names as first row

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.list.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.list lists any dataset that is registered in the temporal database.
Datasets are raster, 3D raster and vector maps as well as their
corresponding space time datasets (STRDS, STR3DS and STVDS). The type of
the dataset can be specified using the type option, default is STRDS.
By default all datasets with relative and absolute time are listed.
However, the user has the ability to specify a single temporal type with
the temporaltype option. The user can define the columns that should
be printed for each dataset and the order of the datasets. In addition a
SQL WHERE statement can be specified to select a subset of the requested
datasets.

---

## See Also

Related tools:
- [`g.list`](https://grass.osgeo.org/grass-devel/manuals/g.list.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`t.rast.list`](https://grass.osgeo.org/grass-devel/manuals/t.rast.list.html)
- [`t.rast3d.list`](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.list.html)
- [`t.vect.list`](https://grass.osgeo.org/grass-devel/manuals/t.vect.list.html)

---

## Resources

- [Official t.list manual](https://grass.osgeo.org/grass-devel/manuals/t.list.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.list.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
