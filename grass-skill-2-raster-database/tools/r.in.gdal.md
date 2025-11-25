# r.in.gdal

**Category**: raster

## Description

Imports raster data into a GRASS raster map using GDAL library.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_in_gdal(input,output,band=None,memory=300,target=None,title=None,offset=0,num_digits=0,map_names_file=None,project=None,table=None,gdal_config=None,gdal_doo=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of raster file to be imported
   - Used as: input, file, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`band : int | list[int] | str, optional`**
   - Band(s) to select (default is all bands)

4. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

5. **`target : str, optional`**
   - Name of GCPs target project (location)
   - Name of project to create or to read CRS from for GCPs transformation
   - Used as: name

6. **`title : str, optional`**
   - Title for resultant raster map
   - Used as: phrase

7. **`offset : int, optional`**
   - Offset to be added to band numbers
   - If 0, no offset is added and the first band is 1
   - Default: 0

8. **`num_digits : int, optional`**
   - Zero-padding of band number by filling with leading zeros up to given number
   - If 0, length will be adjusted to 'offset' number without leading zeros
   - Default: 0

9. **`map_names_file : str, optional`**
   - Name of the output file that contains the imported map names
   - Used as: output, file, name

10. **`project : str, optional`**
   - Name for new project (location) to create
   - Used as: name

11. **`table : str, optional`**
   - File prefix for raster attribute tables
   - The band number and ".csv" will be appended to the file prefix
   - Used as: file

12. **`gdal_config : str, optional`**
   - GDAL configuration options
   - Comma-separated list of key=value pairs

13. **`gdal_doo : str, optional`**
   - GDAL dataset open options
   - Comma-separated list of key=value pairs

14. **`flags : str, optional`**
   - Allowed values: o, j, e, f, l, a, k, c, r, p
   - o
   - Override projection check (use current project's CRS)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html#__tabbed_2_3) for all details)*

15. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

16. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

17. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

18. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 18 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.in.gdal allows a user to create a GRASS raster map layer, or
imagery group, from any GDAL supported raster map format, with an
optional title. The imported file may also be used to create a new
project (previously called location).

Full details on all GDAL supported formats are available at:

https://gdal.org/en/stable/drivers/raster/

Selected formats out of the more than 140 supported formats:

r.in.gdal attempts to preserve coordinate reference system (CRS)
information when importing datasets if the source format includes CRS
information, and if the GDAL driver supports it. If the CRS of the
source dataset does not match the CRS of the current project r.in.gdal will report an error message
( Coordinate reference system of dataset does not appear to match current project )
and then report the PROJ_INFO parameters of the source dataset.

If the user wishes to ignore the difference between the apparent
coordinate system of the source data and the current project, they may
pass the -o flag to override the CRS check.

If the user wishes to import the data with the full CRS definition, it
is possible to have r.in.gdal automatically create a new project based
on the CRS and extents of the file being read. This is accomplished by
passing the name to be used for the new project via the project parameter. Upon completion of the command, a new project will have been
created (with only a PERMANENT mapset), and the raster will have been
imported with the indicated output name into the PERMANENT mapset.

In case the image contains Ground Control Points (GCP) they are written
to a POINTS file within an imagery group. They can directly be used for i.rectify .

The target option allows you to automatically re-project the GCPs
from their own CRS into another CRS read from the PROJ_INFO file of the
project name target .

If the target project does not exist, a new project will be created
matching the CRS definition of the GCPs. The target of the output group
will be set to the new project, and i.rectify can now be
used without any further preparation.

Some satellite images (e.g. NOAA/AVHRR, ENVISAT) can contain hundreds or
thousands of GCPs. In these cases thin plate spline coordinate
transformation is recommended, either before import with gdalwarp
-tps or after import with i.rectify -t .

The offset parameter allows adding an offset to band number(s) which
is convenient in case of the import of e.g. a continuous time series
split across different input files.

The num_digits parameter allows defining the number of leading zeros
(zero padding) in case of band numbers (e.g., to turn band.1 into band.001 ).

---

## See Also

Related tools:
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r.import`](https://grass.osgeo.org/grass-devel/manuals/r.import.html)
- [`r.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.in.ascii.html)
- [`r.in.bin`](https://grass.osgeo.org/grass-devel/manuals/r.in.bin.html)
- [`r.null`](https://grass.osgeo.org/grass-devel/manuals/r.null.html)
- [`t.register`](https://grass.osgeo.org/grass-devel/manuals/t.register.html)

---

## Resources

- [Official r.in.gdal manual](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
