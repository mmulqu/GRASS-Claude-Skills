# g.list

**Category**: general

## Description

Lists available GRASS data base files of the user-specified data type optionally using the search pattern.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_list(type,pattern=None,exclude=None,mapset=None,separator="newline",region=None,output=None,format=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`type : str | list[str], required`**
   - Data type(s)
   - Used as: datatype
   - Allowed values: raster, raster_3d, vector, label, region, group, all
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.list.html#__tabbed_2_3) for all details)*

2. **`pattern : str, optional`**
   - Map name search pattern (default: all)

3. **`exclude : str, optional`**
   - Map name exclusion pattern (default: none)

4. **`mapset : str | list[str], optional`**
   - Name of mapset to list (default: current search path)
   - '.' for current mapset; '*' for all mapsets in location
   - Used as: input, mapset, name

5. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

6. **`region : str, optional`**
   - Name of saved region for map search (default: not restricted)
   - '.' for current region; '*' for default region
   - Used as: input, region, name

7. **`output : str, optional`**
   - Name for output file
   - If not given or '-' then standard output
   - Used as: output, file, name

8. **`format : str, optional`**
   - Output format
   - Used as: name
   - Allowed values: plain, shell, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.list.html#__tabbed_2_3) for all details)*

9. **`flags : str, optional`**
   - Allowed values: i, r, e, t, m, p, f
   - i
   - Ignore case
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.list.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/g.list.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

g.list searches for data files matching a pattern given by wildcards
or POSIX Extended Regular Expressions.

---

## See Also

Related tools:
- [`r.series`](https://grass.osgeo.org/grass-devel/manuals/r.series.html)
- [`t.list`](https://grass.osgeo.org/grass-devel/manuals/t.list.html)
- [`t.rast.list`](https://grass.osgeo.org/grass-devel/manuals/t.rast.list.html)
- [`t.vect.list`](https://grass.osgeo.org/grass-devel/manuals/t.vect.list.html)

---

## Resources

- [Official g.list manual](https://grass.osgeo.org/grass-devel/manuals/g.list.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.list.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
