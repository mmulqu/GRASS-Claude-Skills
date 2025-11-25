# g.download.project

**Category**: general

## Description

Download GRASS project from the web Get GRASS project from an URL or file path

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_download_project(url,name=None,path=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`url : str, required`**
   - URL of the archive with a project to be downloaded
   - URL of ZIP, TAR.GZ, or other similar archive

2. **`name : str, optional`**
   - Project (location) name
   - Project name (not path to project)
   - Used as: input, location, name

3. **`path : str, optional`**
   - GRASS database directory
   - Default: path to the current GRASS database
   - Used as: input, dbase, path

4. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

5. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

6. **`superquiet : bool, optional`**
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

g.download.project downloads an archived (e.g., .zip or .tar.gz )
project (previously called location) from a given URL and unpacks it to
a specified or current GRASS Spatial Database. URL can be also a
local file on the disk. If the archive contains a directory which
contains a project, the module will recognize that and use the project
automatically. The first directory which is a project is used. Other
projects or any other files are ignored.

---

## See Also

Related tools:
- [`g.mapset`](https://grass.osgeo.org/grass-devel/manuals/g.mapset.html)
- [`g.mapsets`](https://grass.osgeo.org/grass-devel/manuals/g.mapsets.html)
- [`r.proj`](https://grass.osgeo.org/grass-devel/manuals/r.proj.html)
- [`v.proj`](https://grass.osgeo.org/grass-devel/manuals/v.proj.html)
- [`g.proj.all`](https://grass.osgeo.org/grass-devel/manuals/g.proj.all.html)

---

## Resources

- [Official g.download.project manual](https://grass.osgeo.org/grass-devel/manuals/g.download.project.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.download.project.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
