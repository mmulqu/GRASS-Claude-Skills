# t.rast.what

**Category**: temporal

## Description

Sample a space time raster dataset at specific vector point coordinates and write the output to stdout using different layouts

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_what(points=None,coordinates=None,strds,output="-",where=None,null_value=None,separator="pipe",order="start_time",layout="row",nprocs=1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`points : str, optional`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`coordinates : tuple[float, float] | list[float] | str, optional`**
   - Comma separated list of coordinates
   - Used as: input, coords, east,north

3. **`strds : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

4. **`output : str, optional`**
   - Name for the output file or "-" in case stdout should be used
   - Used as: output, file, name
   - Default: -

5. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

6. **`null_value : str, optional`**
   - String representing NULL value
   - Used as: string

7. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

8. **`order : str | list[str], optional`**
   - Sort the maps by category
   - Allowed values: id,  name,  creator,  mapset,  creation_time,  modification_time,  start_time,  end_time,  north,  south,  west,  east,  min,  max
   - Default: start_time

9. **`layout : str, optional`**
   - The layout of the output. One point per row (row), one point per column (col), all timsteps in one row (timerow)
   - Allowed values: row,  col,  timerow
   - Default: row

10. **`nprocs : int, optional`**
   - Number of r.what processes to run in parallel
   - Default: 1

11. **`flags : str, optional`**
   - Allowed values: n, i, v
   - n
   - Output header row
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.what.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.what.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast.what is designed to sample space time raster datasets at
specific point coordinates using r.what internally. The
output of r.what is transformed to different output
layouts. The output layouts can be specified using the layout option.

Three layouts can be specified:

Please have a look at the example to see the supported layouts.

This module is designed to run several instances of r.what to sample
subsets of a space time raster dataset in parallel. Several intermediate
text files will be created that are merged into a single file at the end
of the processing.

Coordinates can be provided as vector map using the points option or
as comma separated coordinate list with the coordinates option.

An output file can be specified using the output option. Stdout will
be used if no output is specified or if the output option is set to
"-".

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.mask`](https://grass.osgeo.org/grass-devel/manuals/r.mask.html)
- [`r.neighbors`](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)
- [`r.what`](https://grass.osgeo.org/grass-devel/manuals/r.what.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`t.rast.aggregate.ds`](https://grass.osgeo.org/grass-devel/manuals/t.rast.aggregate.ds.html)
- [`t.rast.extract`](https://grass.osgeo.org/grass-devel/manuals/t.rast.extract.html)
- [`v.what.strds`](https://grass.osgeo.org/grass-devel/manuals/v.what.strds.html)

---

## Resources

- [Official t.rast.what manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.what.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.what.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
