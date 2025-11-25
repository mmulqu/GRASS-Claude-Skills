# g.filename

**Category**: general

## Description

Prints GRASS data base file names.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_filename(element,file,mapset=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`element : str, required`**
   - Name of an element

2. **`file : str, required`**
   - Name of a database file

3. **`mapset : str, optional`**
   - Name of a mapset (default: current)

4. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Create element directory in the current mapset

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

g.filename is designed for Bourne shell scripts that need to know the
full file name, including it's path, for mapset elements, like raster,
vector and site maps, region definitions and imagery groups.

The list of element names to search for is not fixed; any subdirectory
of the mapset directory is a valid element name.

However, the user can find the list of standard GRASS element names
in the file $GISBASE/etc/element_list . This is the file which
g.remove/g.rename/g.copy use to determine which files need to be
deleted/renamed/copied for a given entity type.

---

## See Also

Related tools:
- [`g.findfile`](https://grass.osgeo.org/grass-devel/manuals/g.findfile.html)
- [`g.gisenv`](https://grass.osgeo.org/grass-devel/manuals/g.gisenv.html)

---

## Resources

- [Official g.filename manual](https://grass.osgeo.org/grass-devel/manuals/g.filename.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.filename.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
