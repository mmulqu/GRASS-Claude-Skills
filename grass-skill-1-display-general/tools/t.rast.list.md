# t.rast.list

**Category**: temporal

## Description

Lists registered maps of a space time raster dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_list(input,order=None,columns=None,where=None,method="list",granule=None,format=None,separator="pipe",output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`order : str | list[str], optional`**
   - Sort the space time dataset by category
   - Allowed values: id, name, semantic_label, creator, mapset, temporal_type, creation_time, start_time, end_time, north, south, west, east, nsres, ewres, cols, rows, number_of_cells, min, max

3. **`columns : str | list[str], optional`**
   - Columns to be printed to stdout
   - Allowed values: id, name, semantic_label, creator, mapset, temporal_type, creation_time, start_time, end_time, north, south, west, east, nsres, ewres, cols, rows, number_of_cells, min, max, interval_length, distance_from_begin

4. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

5. **`method : str, optional`**
   - Method used for data listing
   - Allowed values: list, cols, comma, delta, deltagaps, gran

6. **`Default: list`**

7. **`granule : str, optional`**
   - The granule to be used for listing. The granule must be specified as string eg.: absolute time "1 months" or relative time "1"

8. **`format : str, optional`**
   - Output format
   - Allowed values: plain, line, json, yaml, csv

9. **`separator : str, optional`**
   - Field separator character between the output columns
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

10. **`output : str, optional`**
   - Name for output file
   - Used as: output, file, name

11. **`flags : str, optional`**
   - Allowed values: u
   - u
   - Suppress printing of column names

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


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.list.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

List time stamped raster map layers that are registered in a space time
raster dataset. t.rast.list provides several options to list map
layers and their metadata. Listing of map layer can be ordered by
metadata, metadata columns can be specified and SQL where conditions can
be provided to select a map layer subset of the input space time raster
dataset. Most of the raster map specific metadata is available for
column selection, sorting and SQL where statements. Using the method option allows the specification of different methods to list map layers.
Method list is the default option and sensitive to the column , order and where options.

To print interval length in days and distance from the begin use method delta . Method deltagap will additionally print temporal gaps between
map layer. The gran method allows the listing of map layer sampled by
a user defined granule . As default the granularity of the space time
raster dataset is used for sampling.

While method list supports all columns except for interval_length and
distance_from_begin, methods delta , deltagap , and gran support
only the following columns: id, name, mapset, start_time, end_time,
interval_length, and distance_from_begin. The option order is only
available with method list .

Methods cols and comma are depreciated. The cols method is
replaced by the plain format and the comma method is replaced by the line format.

The format option specifies the format of the output data. The
default plain format will simply print user specified metadata columns
of one map layer per line separated by a pipe by default. The line format will list fully qualified map names (name and mapset) as a
comma-separated list of values that can be used as input for spatial
modules. The csv format will print data in the CSV format using comma
as the value separator (delimiter) and double quote for text field
quoting. The json format generates JSON and, if the PyYAML package is
installed, The yaml format generates YAML. The column (or item)
separator can be specified with the separator option for plain , line , and csv .

---

## See Also

Related tools:
- [`g.list`](https://grass.osgeo.org/grass-devel/manuals/g.list.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`t.list`](https://grass.osgeo.org/grass-devel/manuals/t.list.html)
- [`t.rast3d.list`](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.list.html)
- [`t.vect.list`](https://grass.osgeo.org/grass-devel/manuals/t.vect.list.html)

---

## Resources

- [Official t.rast.list manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.list.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.list.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
