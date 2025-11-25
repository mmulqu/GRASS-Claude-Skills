# g.findetc

**Category**: general

## Description

Searches for GRASS support files.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_findetc(file,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`file : str, required`**
   - Name of an file or directory

2. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

3. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

4. **`superquiet : bool, optional`**
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

g.findetc is designed for Bourne shell scripts that need to search for
support data, programs and subfoldrs in any number of directories as
specified in GRASS_ADDON_ETC, plus the GRASS application etc/ directory.
This is designed for addon scripts that are installed outside the GRASS
application directory, such as a user's home or a system addon
directory.

---

## See Also

Related tools:
- [`g.filename`](https://grass.osgeo.org/grass-devel/manuals/g.filename.html)
- [`g.findfile`](https://grass.osgeo.org/grass-devel/manuals/g.findfile.html)
- [`g.gisenv`](https://grass.osgeo.org/grass-devel/manuals/g.gisenv.html)
- [`g.mapsets`](https://grass.osgeo.org/grass-devel/manuals/g.mapsets.html)

---

## Resources

- [Official g.findetc manual](https://grass.osgeo.org/grass-devel/manuals/g.findetc.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.findetc.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
