# v.import

**Category**: vector

## Description

Imports vector data into a GRASS vector map using OGR library and reprojects on the fly.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_import(input,layer=None,output=None,extent="input",encoding=None,snap=-1,epsg=None,datum_trans=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of OGR datasource to be imported
   - Used as: input, datasource

2. **`layer : str | list[str], optional`**
   - OGR layer name. If not given, all available layers are imported
   - Used as: input, datasource_layer

3. **`output : str, optional`**
   - Name for output vector map (default: input)
   - Used as: output, vector, name

4. **`extent : str, optional`**
   - Output vector map extent
   - Allowed values: input, region
   - input: extent of input map
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.import.html#__tabbed_2_3) for all details)*

5. **`encoding : str, optional`**
   - Encoding value for attribute data

6. **`snap : float, optional`**
   - Snapping threshold for boundaries (map units)
   - A suitable threshold is estimated during import
   - Default: -1

7. **`epsg : int, optional`**
   - EPSG projection code
   - Allowed values: 1-1000000

8. **`datum_trans : int, optional`**
   - Index number of datum transform parameters
   - -1 to list available datum transform parameters
   - Allowed values: -1-100

9. **`flags : str, optional`**
   - Allowed values: f, l, o
   - f
   - List supported OGR formats and exit
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.import.html#__tabbed_2_3) for all details)*

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.import.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.import imports vector data from files and database connections
supported by the OGR library into the current
project (previously called location) and mapset. If the coordinate
reference system (CRS) of the input does not match the CRS of the
project, the input is reprojected into the current project. In case that
the CRS of the input map does match the CRS of the project, the input is
imported directly.

v.import uses the OGR library which supports various vector data
formats including ESRI
Shapefile , Mapinfo File , UK
.NTF, SDTS, TIGER, IHO S-57 (ENC), DGN, GML, GPX, AVCBin, REC, Memory,
OGDI, and PostgreSQL, depending on the local OGR installation. For
details see the OGR web
site . The OGR (Simple
Features Library) is part of the GDAL library, hence
GDAL needs to be installed to use v.import .

The list of actually supported formats can be printed by -f flag.

---

## See Also

Related tools:
- [`v.clean`](https://grass.osgeo.org/grass-devel/manuals/v.clean.html)
- [`v.in.lines`](https://grass.osgeo.org/grass-devel/manuals/v.in.lines.html)
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)
- [`v.proj`](https://grass.osgeo.org/grass-devel/manuals/v.proj.html)

---

## Authors

Markus Metz Improvements: Martin Landa, Anna Petrasova

---

## Resources

- [Official v.import manual](https://grass.osgeo.org/grass-devel/manuals/v.import.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.import.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
