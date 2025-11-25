# t.rast.export

**Category**: temporal

## Description

Exports space time raster dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_export(input,output,directory="./",compression="bzip2",format="GTiff",type=None,createopt=None,metaopt=None,nodata=None,where=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`output : str, required`**
   - Name of a space time raster dataset archive
   - Used as: output, file, name

3. **`directory : str, optional`**
   - Path to the directory where output is written
   - If not given, the default is the current working directory
   - Used as: input, dir, name

4. **`compression : str, optional`**
   - Compression method of the tar archive
   - Allowed values: no, gzip, bzip2
   - Default: bzip2

5. **`format : str, optional`**
   - The export format of a single raster map
   - Supported are GTiff, AAIGrid via r.out.gdal and the GRASS package format of r.pack
   - Allowed values: GTiff, AAIGrid, pack

6. **`type : str, optional`**
   - Data type
   - Supported only for GTiff
   - Allowed values: Byte, Int16, UInt16, Int32, UInt32, Float32, Float64, CInt16, CInt32, CFloat32, CFloat64

7. **`createopt : str | list[str], optional`**
   - Creation option(s) to pass to the output format driver
   - In the form of "NAME=VALUE", separate multiple entries with a comma

8. **`metaopt : str | list[str], optional`**
   - Metadata key(s) and value(s) to include
   - In the form of "META-TAG=VALUE", separate multiple entries with a comma. Not supported by all output format drivers.

9. **`nodata : float, optional`**
   - Assign a specified nodata value to output bands
   - If given, the nodata value is always written to metadata even if there are no NULL cells in the input band (enhances output compatibility).

10. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

11. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

12. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

13. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

14. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.export.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast.export exports a space time raster dataset (strds) as a tar
archive. The archive contains the raster maps either as GeoTIFF files or
as GRASS binary files exported using r.pack . The map specific color
tables are exported in case of GeoTIFF files. In addition several
metadata files are created in the archive that describe the temporal
layout. All time stamps are stored in the file "list.txt", for each map
one row. The name of the map, the start time and the end time are
written. In case of a time instance, the start time is equal to the end
time. The "init.txt" file stores the temporal type, the number of maps,
the chosen export format and some other metadata. The "proj.txt" file
stores the coordinate reference system information as a proj4 string of
the project the space time raster dataset was exported from. The file
"readme.txt" describes the file format. The output of r.info for each
raster map in the space time dataset is stored in "metadata.txt".

The tar archive can be compressed using the compress option. Gzip
and bzip2 (default) are available. A where option can be specified,
to export only a subset of the space time dataset. Archives exported
with t.rast.export can be imported with t.rast.import .

---

## See Also

Related tools:
- [`t.rast.import`](https://grass.osgeo.org/grass-devel/manuals/t.rast.import.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`r.out.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.out.gdal.html)
- [`r.pack`](https://grass.osgeo.org/grass-devel/manuals/r.pack.html)
- [`t.vect.export`](https://grass.osgeo.org/grass-devel/manuals/t.vect.export.html)

---

## Resources

- [Official t.rast.export manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.export.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.export.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
