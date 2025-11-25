# r.info

**Category**: raster

## Description

Outputs basic information about a raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_info(map,format=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map
   - Used as: input, raster, name

2. **`format : str, optional`**
   - Output format
   - Used as: name
   - Allowed values: plain, shell, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.info.html#__tabbed_2_3) for all details)*

3. **`flags : str, optional`**
   - Allowed values: g, r, s, e, h
   - g
   - Print raster array information
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.info.html#__tabbed_2_3) for all details)*

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

r.info reports some basic information about a user-specified raster
map layer. This map layer must exist in the user's current mapset search
path. Information about the map's boundaries, resolution, projection,
data type, category number, project, mapset, project parent directory
(database directory), the timestamp and history are put into a table and
written to standard output. The types of information listed can also be
found in the cats , cellhd , and hist directories under the mapset
in which the named map is stored.

The user can save the tabular output to a file by using the UNIX
redirection mechanism (>); for example, the user might save a report on
the soils map layer in a file called soil.txt by typing:

---

## See Also

Related tools:
- [`g.mapsets`](https://grass.osgeo.org/grass-devel/manuals/g.mapsets.html)
- [`r.coin`](https://grass.osgeo.org/grass-devel/manuals/r.coin.html)
- [`r.describe`](https://grass.osgeo.org/grass-devel/manuals/r.describe.html)
- [`r.report`](https://grass.osgeo.org/grass-devel/manuals/r.report.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)
- [`r.what`](https://grass.osgeo.org/grass-devel/manuals/r.what.html)

---

## Resources

- [Official r.info manual](https://grass.osgeo.org/grass-devel/manuals/r.info.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.info.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
