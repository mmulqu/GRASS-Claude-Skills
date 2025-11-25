# g.proj

**Category**: general

## Description

Prints or modifies GRASS projection information files (in various co-ordinate system descriptions). Can also be used to create new GRASS projects.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_proj(georef=None,wkt=None,srid=None,proj4=None,epsg=None,list_codes=None,datum=None,datum_trans=0,project=None,format="plain",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`georef : str, optional`**
   - Name of georeferenced data file to read projection information from
   - Used as: file

2. **`wkt : str, optional`**
   - Name of ASCII file containing a WKT projection description
   - '-' for standard input
   - Used as: file

3. **`srid : str, optional`**
   - Spatial reference ID with authority name and code
   - E.g. EPSG:4326 or urn:ogc:def:crs:EPSG::4326
   - Used as: params

4. **`proj4 : str, optional`**
   - PROJ.4 projection description
   - '-' for standard input
   - Used as: params

5. **`epsg : int, optional`**
   - EPSG projection code
   - Used as: code
   - Allowed values: 1-1000000

6. **`list_codes : str, optional`**
   - List codes for given authority, e.g. EPSG, and exit
   - Allowed values: EPSG, ESRI, IAU_2015, IGNF, NKG, NRCAN, OGC, PROJ

7. **`datum : str, optional`**
   - Datum (overrides any datum specified in input co-ordinate system)
   - Accepts standard GRASS datum codes, or "list" to list and exit
   - Used as: name

8. **`datum_trans : int, optional`**
   - Index number of datum transform parameters
   - "0" for unspecified or "-1" to list and exit
   - Used as: index
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.proj.html#__tabbed_2_3) for all details)*

9. **`project : str, optional`**
   - Name of new project (location) to create
   - Used as: name

10. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, shell, json, wkt, proj4
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.proj.html#__tabbed_2_3) for all details)*

11. **`flags : str, optional`**
   - Allowed values: p, g, d, j, f, w, e, t, c
   - p
   - Print projection information
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.proj.html#__tabbed_2_3) for all details)*

12. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

13. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

14. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/g.proj.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

g.proj provides a means of converting a coordinate reference system
(CRS) description between various formats.

For an introduction to map projections (with PROJ),see the manual page
of r.proj .

If compiled without OGR present, the functionality
is limited to:

When compiled with OGR, functionality is increased and allows output of
the CRS information in the Well-Known Text (WKT) format popularised by
proprietary GIS. In addition, if one of the parameters georef , wkt , proj4 or epsg is specified, rather than being read from the current
project, the CRS information is imported from an external source as
follows:

If datum information is incorrect or missing in the input co-ordinate
system definition (e.g. PROJ descriptions have very limited support for
specifying datum names), a GRASS datum abbreviation can instead be
supplied using the datum parameter. This will override any datum
contained in the input co-ordinate system, and discard any datum
transformation parameters. Enter datum= list to return a list of all
the datums supported by GRASS. Since any existing datum transformation
parameters will have been discarded, the datumtrans parameter should
in general always be used in conjunction with datum .

The -p , -j , -w , etc. flags are all functional when importing
CRS information from an external source, meaning that g.proj can be
used to convert between representations of the information. It is not required that either the input or output be in GRASS format.

In addition however, if the -c flag is specified, g.proj will
create new GRASS CRS files (PROJ_INFO, PROJ_UNITS, WIND and
DEFAULT_WIND) based on the imported information. If the project parameter is specified in addition to -c , then a new project will be
created. Otherwise the CRS information files in the current project will
be overwritten. The program will not warn before doing this.

The final mode of operation of g.proj is to report on the datum
information and datum transformation parameters associated with the
co-ordinate system. The -d flag will report a human-readable summary
of this.

---

## See Also

Related tools:
- [`m.proj`](https://grass.osgeo.org/grass-devel/manuals/m.proj.html)
- [`r.proj`](https://grass.osgeo.org/grass-devel/manuals/r.proj.html)
- [`v.proj`](https://grass.osgeo.org/grass-devel/manuals/v.proj.html)
- [`r.import`](https://grass.osgeo.org/grass-devel/manuals/r.import.html)
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`v.import`](https://grass.osgeo.org/grass-devel/manuals/v.import.html)
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)

---

## Resources

- [Official g.proj manual](https://grass.osgeo.org/grass-devel/manuals/g.proj.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.proj.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
