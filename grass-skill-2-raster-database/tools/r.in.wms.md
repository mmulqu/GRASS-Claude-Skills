# r.in.wms

**Category**: raster

## Description

Downloads and imports data from OGC WMS and OGC WMTS web mapping servers.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_in_wms(url,output,layers,styles=None,format="png",srs=4326,driver="WMS_GRASS",wms_version="1.1.1",maxcols=512,maxrows=512,urlparams=None,username=None,password=None,method="nearest",gdal_createopt=None,region=None,bgcolor=None,proxy=None,proxy_user_pw=None,capfile=None,capfile_output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`url : str, required`**
   - Typically starts with "http://"

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`layers : str | list[str], required`**
   - Layer(s) to request from the map server

4. **`styles : str | list[str], optional`**
   - Layer style(s) to request from the map server

5. **`format : str, optional`**
   - Image format requested from the server
   - Allowed values: geotiff, tiff, jpeg, gif, png, png8
   - Default: png

6. **`srs : int, optional`**
   - EPSG code of requested source projection
   - Default: 4326

7. **`driver : str, optional`**
   - Driver used for communication with the server
   - Allowed values: WMS_GDAL,  WMS_GRASS,  WMTS_GRASS,  OnEarth_GRASS
   - WMS_GDAL: Download data using GDAL WMS driver
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.in.wms.html#__tabbed_2_3) for all details)*

8. **`wms_version : str, optional`**
   - WMS standard version
   - Allowed values: 1.1.0, 1.1.1, 1.3.0
   - Default: 1.1.1

9. **`maxcols : int, optional`**
   - Maximum columns to request at a time
   - Default: 512

10. **`maxrows : int, optional`**
   - Maximum rows to request at a time
   - Default: 512

11. **`urlparams : str, optional`**
   - Additional query parameters to pass to the server

12. **`username : str, optional`**
   - Username for server connection

13. **`password : str, optional`**
   - Password for server connection

14. **`method : str, optional`**
   - Interpolation method to use in reprojection
   - Allowed values: nearest, linear, cubic, cubicspline
   - Default: nearest

15. **`gdal_createopt : str | list[str], optional`**
   - GDAL creation option(s) to pass to the output format driver
   - In the form of "NAME=VALUE", separate multiple entries with a comma

16. **`region : str, optional`**
   - Request data for this named region instead of the current region bounds

17. **`bgcolor : str, optional`**
   - Background color
   - Format: 0xRRGGBB

18. **`proxy : str, optional`**
   - HTTP proxy only GDAL driver (GDAL_HTTP_PROXY)
   - HTTP proxy

19. **`proxy_user_pw : str, optional`**
   - User and password for HTTP proxy only for GDAL driver (GDAL_HTTP_PROXYUSERPWD). Must be in the form of [user name]:[password].
   - User and password for HTTP proxy

20. **`capfile : str, optional`**
   - Capabilities file to parse (input). It is relevant for WMTS_GRASS and OnEarth_GRASS drivers
   - Used as: input, file, name

21. **`capfile_output : str, optional`**
   - File where the server capabilities will be saved ('c' flag)
   - Used as: output, file, name

22. **`flags : str, optional`**
   - Allowed values: c, o, b
   - c
   - Get the server capabilities, print them out, then exit
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.in.wms.html#__tabbed_2_3) for all details)*

23. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

24. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

25. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

26. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 26 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.wms.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.in.wms handles all of downloading and importing raster data from OGC WMS and OGC
WMTS web mapping
servers. It only needs be told the desired data to collect (bounds and
resolution) via a region, the server to get the data from, and the layer
or layers to get. It downloads the data in tiles, reprojects it, imports
it, and patches it back together.

---

## See Also

Related tools:
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`r.patch`](https://grass.osgeo.org/grass-devel/manuals/r.patch.html)
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r.composite`](https://grass.osgeo.org/grass-devel/manuals/r.composite.html)
- [`v.in.wfs`](https://grass.osgeo.org/grass-devel/manuals/v.in.wfs.html)

---

## Resources

- [Official r.in.wms manual](https://grass.osgeo.org/grass-devel/manuals/r.in.wms.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.wms.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
