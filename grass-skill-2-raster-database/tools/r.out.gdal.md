# r.out.gdal

**Category**: raster

## Description

Exports GRASS raster maps into GDAL supported formats.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_out_gdal(input,output,format="GTiff",type=None,createopt=None,metaopt=None,nodata=None,overviews=0,offset=None,scale=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of raster map (or group) to export
   - Used as: input, raster, name

2. **`output : str, required`**
   - Name for output raster file
   - Used as: output, file, name

3. **`format : str, required`**
   - Raster data format to write (case sensitive, see also -l flag)
   - Allowed values: VRT, GTiff, COG, NITF, HFA, AAIGrid, DTED, PNG, JPEG, MEM, GIF, FITS, BMP, PCIDSK, PCRaster, ILWIS, SRTMHGT, Leveller, Terragen, netCDF, HDF4Image, ISIS3, PDS4, VICAR, ERS, JP2OpenJPEG, GRIB, RMF, WMS, RST, GSAG, GSBG, GS7BG, KMLSUPEROVERLAY, WEBP, PDF, MBTiles, CALS, WMTS, MRF, PNM, BT, LCP, GTX, KRO, ROI_PAC, RRASTER, BAG, NWT_GRD, PostGISRaster, SAGA, XYZ, HF2, ZMap, SIGDEM, AVIF, HEIF, JPEGXL, GPKG, OpenFileGDB, NGW, ENVI, EHdr, ISCE, Zarr
   - Default: GTiff

4. **`type : str, optional`**
   - Data type
   - Allowed values: Byte, Int16, UInt16, Int32, UInt32, Float32, Float64, CInt16, CInt32, CFloat32, CFloat64

5. **`createopt : str | list[str], optional`**
   - Creation option(s) to pass to the output format driver
   - In the form of "NAME=VALUE", separate multiple entries with a comma

6. **`metaopt : str | list[str], optional`**
   - Metadata key(s) and value(s) to include
   - In the form of "META-TAG=VALUE", separate multiple entries with a comma. Not supported by all output format drivers.

7. **`nodata : float, optional`**
   - Assign a specified nodata value to output bands
   - If given, the nodata value is always written to metadata even if there are no NULL cells in the input band (enhances output compatibility).

8. **`overviews : int, optional`**
   - Number of overviews to create for the output dataset
   - Allowed values: 0-5
   - Default: 0

9. **`offset : float, optional`**
   - Assign a specified offset value to output bands

10. **`scale : float, optional`**
   - Assign a specified scale value to output bands

11. **`flags : str, optional`**
   - Allowed values: l, c, m, t, f
   - l
   - List supported output formats
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.out.gdal.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.gdal.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.out.gdal allows a user to export a GRASS raster map layer into any
GDAL supported raster map format. If a GRASS raster map is exported for
a particular application, the application's native format would be
preferable. GeoTIFF is supported by a wide range of applications (see
also NOTES on GeoTIFF below).

To specify multiple creation options use a comma separated list
( createopt="TFW=YES,COMPRESS=DEFLATE" ).

For possible createopt and metaopt parameters please consult the
individual supported
formats pages on the GDAL
website. The createopt parameter may be used to create TFW or World
files ("TFW=YES","WORLDFILE=ON").

r.out.gdal also supports the export of multiband rasters as a group,
when the imagery group's name is entered as input. (created imagery
groups with the i.group module)

As with most GRASS raster modules, the current region extents and region
resolution are used, and a raster mask is respected if present. Use g.region 's "align=", or "raster=" options if you need
to realign the region settings to match the original map's before
export.

---

## Authors

Vytautas Vebra (oliver4grass at gmail.com) Markus Metz (improved nodata logic)

---

## Resources

- [Official r.out.gdal manual](https://grass.osgeo.org/grass-devel/manuals/r.out.gdal.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.gdal.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
