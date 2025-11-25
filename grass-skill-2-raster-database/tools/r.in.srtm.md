# r.in.srtm

**Category**: raster

## Description

Imports SRTM HGT files into raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_in_srtm(input,output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - Name of SRTM input tile (file without .hgt.zip extension)
   - Used as: input, file, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map (default: input tile)
   - Used as: output, raster, name

3. **`flags : str, optional`**
   - Allowed values: 1
   - 1
   - Input is a 1-arcsec tile (default: 3-arcsec)

4. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.in.srtm imports SRTM HGT files into GRASS. SRTM Version 1 and
improved Version 2 data sets can be downloaded from NASA at this site: http://dds.cr.usgs.gov/srtm/ (archived) https://earthexplorer.usgs.gov/

Gap-filled SRTM Version 3 data can be downloaded from USGS at this
site: https://e4ftl01.cr.usgs.gov/MEASURES/SRTMGL3.003/2000.02.11/

---

## See Also

Related tools:
- [`r.in.bin`](https://grass.osgeo.org/grass-devel/manuals/r.in.bin.html)
- [`r.in.srtm.region`](https://grass.osgeo.org/grass-devel/manuals/r.in.srtm.region.html)
- [`r.in.nasadem`](https://grass.osgeo.org/grass-devel/manuals/r.in.nasadem.html)

---

## Authors

Markus Neteler Improved by W. Kyngesburye and H. Bowman Update for SRTM V3 by Markus Metz

---

## Resources

- [Official r.in.srtm manual](https://grass.osgeo.org/grass-devel/manuals/r.in.srtm.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.srtm.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
