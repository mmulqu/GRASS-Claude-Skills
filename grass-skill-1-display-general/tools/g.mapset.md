# g.mapset

**Category**: general

## Description

Changes or reports current mapset. Optionally, creates new mapset or lists available mapsets in given project (location).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_mapset(mapset,project=None,dbase=None,format="plain",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`mapset : str, required`**
   - Name of mapset (default: current search path)
   - Name of mapset where to switch
   - Used as: output, mapset, name

2. **`project : str, optional`**
   - Project (location) name
   - Project name (not path to project)
   - Used as: input, location, name

3. **`dbase : str, optional`**
   - GRASS database directory
   - Default: path to the current GRASS database
   - Used as: input, dbase, path

4. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.mapset.html#__tabbed_2_3) for all details)*

5. **`flags : str, optional`**
   - Allowed values: c, l, p
   - c
   - Create mapset if it doesn't exist
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.mapset.html#__tabbed_2_3) for all details)*

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

g.mapset changes the current working mapset, project (formerly known
as location), or GISDBASE (directory with one or more projects).

With g.mapset , the shell history (i.e. .bash_history file of the
initial project will be used to record the command history.

The g.mapset tool can also report the current mapset and all mapsets in
the current project.

---

## See Also

Related tools:
- [`g.gisenv`](https://grass.osgeo.org/grass-devel/manuals/g.gisenv.html)
- [`g.mapsets`](https://grass.osgeo.org/grass-devel/manuals/g.mapsets.html)

---

## Resources

- [Official g.mapset manual](https://grass.osgeo.org/grass-devel/manuals/g.mapset.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.mapset.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
