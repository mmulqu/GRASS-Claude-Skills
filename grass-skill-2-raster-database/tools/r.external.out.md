# r.external.out

**Category**: raster

## Description

Redirects raster output to file utilizing GDAL library rather than storing in GRASS raster format.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_external_out(directory,extension=None,format,options=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`directory : str, required`**
   - Name of output directory
   - Used as: path

2. **`extension : str, optional`**
   - Extension for output files

3. **`format : str, required`**
   - Format of output files
   - Allowed values: VRT, GTiff, COG, NITF, HFA, AAIGrid, DTED, PNG, JPEG, MEM, GIF, FITS, BMP, PCIDSK, PCRaster, ILWIS, SRTMHGT, Leveller, Terragen, netCDF, HDF4Image, ISIS3, PDS4, VICAR, ERS, JP2OpenJPEG, GRIB, RMF, WMS, RST, GSAG, GSBG, GS7BG, KMLSUPEROVERLAY, WEBP, PDF, MBTiles, CALS, WMTS, MRF, PNM, BT, LCP, GTX, KRO, ROI_PAC, RRASTER, BAG, NWT_GRD, PostGISRaster, SAGA, XYZ, HF2, ZMap, SIGDEM, AVIF, HEIF, JPEGXL, GPKG, OpenFileGDB, NGW, ENVI, EHdr, ISCE, Zarr

4. **`options : str | list[str], optional`**
   - Creation options

5. **`flags : str, optional`**
   - Allowed values: f, r, p
   - f
   - List supported formats and exit
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.external.out.html#__tabbed_2_3) for all details)*

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

r.external.out instructs GRASS to write subsequently generated
raster maps as data files (e.g. GeoTIFF) using GDAL instead of storing
them in GRASS raster format in the current mapset.

Any new raster map is immediately written out through GDAL as a file.

---

## See Also

Related tools:
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`r.out.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.out.gdal.html)
- [`r.external`](https://grass.osgeo.org/grass-devel/manuals/r.external.html)

---

## Resources

- [Official r.external.out manual](https://grass.osgeo.org/grass-devel/manuals/r.external.out.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.external.out.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
