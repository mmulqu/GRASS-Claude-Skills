# v.in.wfs

**Category**: vector

## Description

Imports GetFeature from a WFS server.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_in_wfs(url,output,name=None,layer=None,srs=None,maximum_features=None,start_index=None,version="1.0.0",username=None,password=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`url : str, required`**
   - Base URL starting with 'http' and ending in '?'

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`name : str | list[str], optional`**
   - Comma separated names of data layers to download

4. **`layer : str | list[str], optional`**
   - Name of data layers to import

5. **`srs : str, optional`**
   - Specify alternate spatial reference system (example: EPSG:4326)
   - The given code must be supported by the server, consult the capabilities file

6. **`maximum_features : int, optional`**
   - Maximum number of features to download
   - (default: unlimited)

7. **`start_index : int, optional`**
   - Skip earlier feature IDs and start downloading at this one
   - (default: start with the first feature)

8. **`version : str, optional`**
   - version of WFS, e.g.:1.0.0 or 2.0.0
   - Default: 1.0.0

9. **`username : str, optional`**
   - Username or file with username or environment variable name with username

10. **`password : str, optional`**
   - Password or file with password or environment variable name with password

11. **`flags : str, optional`**
   - Allowed values: l, r
   - l
   - Download server capabilities to 'wms_capabilities.xml' in the current directory and exit
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.in.wfs.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.in.wfs.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.in.wfs imports OGC WFS maps (Web Feature Service) from external
servers.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.in.wms`](https://grass.osgeo.org/grass-devel/manuals/r.in.wms.html)
- [`v.import`](https://grass.osgeo.org/grass-devel/manuals/v.import.html)
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)

---

## Authors

Markus Neteler, Hamish Bowman

---

## Resources

- [Official v.in.wfs manual](https://grass.osgeo.org/grass-devel/manuals/v.in.wfs.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.in.wfs.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
