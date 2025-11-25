# g.findfile

**Category**: general

## Description

Searches for GRASS data base files and sets variables for the shell.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_findfile(element,file,mapset=None,format="shell",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`element : str, required`**
   - Name of an element

2. **`file : str, required`**
   - Name of an existing map

3. **`mapset : str, optional`**
   - Name of a mapset (default: search path)
   - '.' for current mapset

4. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: shell, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.findfile.html#__tabbed_2_3) for all details)*

5. **`flags : str, optional`**
   - Allowed values: n, l, t
   - n
   - Do not add quotes
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.findfile.html#__tabbed_2_3) for all details)*

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
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

g.findfile is designed for Bourne shell or Python scripts that need to
search for mapset elements , including: raster, vector maps, region
definitions and imagery groups.

The list of element names to search for is not fixed; any
subdirectory of the mapset directory is a valid element name.

However, the user can find the list of standard GRASS element names
in the file $GISBASE/etc/element_list . This is the file which g.remove , g.rename and g.copy use to determine which files need to be
deleted/renamed/copied for a given entity type.

---

## See Also

Related tools:
- [`g.filename`](https://grass.osgeo.org/grass-devel/manuals/g.filename.html)
- [`g.gisenv`](https://grass.osgeo.org/grass-devel/manuals/g.gisenv.html)
- [`g.mapsets`](https://grass.osgeo.org/grass-devel/manuals/g.mapsets.html)
- [`g.parser`](https://grass.osgeo.org/grass-devel/manuals/g.parser.html)

---

## Resources

- [Official g.findfile manual](https://grass.osgeo.org/grass-devel/manuals/g.findfile.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.findfile.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
