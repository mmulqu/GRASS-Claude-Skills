# v.in.ogr

**Category**: vector

## Description

Imports vector data into a GRASS vector map using OGR library.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_in_ogr(input,gdal_config=None,gdal_doo=None,layer=None,output=None,spatial=None,where=None,min_area=0.0001,type="",snap=-1,project=None,columns=None,encoding=None,key=None,geometry=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

---

---

## Detailed Description

v.in.ogr imports vector data from files and database connections
supported by the OGR library) into the current
project (previously called location) and mapset.

If the layer parameter is not given, all available OGR layers are
imported as separate GRASS layers into one GRASS vector map. If several
OGR layer names are given, all these layers are imported as separate
GRASS layers into one GRASS vector map.

The optional spatial parameter defines spatial query extents. This
parameter allows the user to restrict the region to a spatial subset
while importing the data. All vector features completely or partially
falling into this rectangle subregion are imported. The -r current
region flag is identical, but uses the current region settings as the
spatial bounds (see g.region ).

v.in.ogr uses the OGR library which supports various vector data
formats including ESRI
Shapefile , Mapinfo File , UK
.NTF, SDTS, TIGER, IHO S-57 (ENC), DGN, GML, GPX, AVCBin, REC, Memory,
OGDI, and PostgreSQL, depending on the local OGR installation. For
details see the OGR format
overview . The -f prints
a list of the vector formats supported by the system's OGR (Simple
Features Library). The OGR (Simple Features Library) is part of the GDAL library, hence GDAL needs to be installed to
use v.in.ogr .

The list of actually supported formats can be printed by -f flag.

Topology cleaning on areas is automatically performed, but may fail in
special cases. In these cases, a snap threshold value is estimated
from the imported vector data and printed out at the end. The vector
data can then be imported again with the suggested snap threshold
value which is incremented by powers of 10 until either an estimated
upper limit for the threshold value is reached or the topology cleaning
on areas was successful. In some cases, manual cleaning might be
required or areas are truly overlapping, e.g. buffers created with
non-topological software.

The min_area threshold value is being specified as area size in map
units with the exception of latitude-longitude projects in which it is
being specified solely in square meters.

The snap threshold value is used to snap boundary vertices to each
other if the distance in map units between two vertices is not larger
than the threshold. Snapping is by default disabled with -1. See also
the v.clean manual.

When importing overlapping polygons, the overlapping parts will become
new areas with multiple categories, one unique category for each
original polygon. An original polygon will thus be converted to multiple
areas with the same shared category. These multiple areas will therefore
also link to the same entry in the attribute table. A single category
value may thus refer to multiple non-overlapping areas which together
represent the original polygon overlapping with another polygon. The
original polygon can be recovered by using v.extract with the desired category value or where statement and the -d flag to dissolve common boundaries.

---

## See Also

Related tools:
- [`db.connect`](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [`v.clean`](https://grass.osgeo.org/grass-devel/manuals/v.clean.html)
- [`v.extract`](https://grass.osgeo.org/grass-devel/manuals/v.extract.html)
- [`v.build.polylines`](https://grass.osgeo.org/grass-devel/manuals/v.build.polylines.html)
- [`v.edit`](https://grass.osgeo.org/grass-devel/manuals/v.edit.html)
- [`v.external`](https://grass.osgeo.org/grass-devel/manuals/v.external.html)
- [`v.import`](https://grass.osgeo.org/grass-devel/manuals/v.import.html)
- [`v.in.db`](https://grass.osgeo.org/grass-devel/manuals/v.in.db.html)
- [`v.in.e00`](https://grass.osgeo.org/grass-devel/manuals/v.in.e00.html)
- [`v.out.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.out.ogr.html)

---

## Authors

Original author: Radim Blazek, ITC-irst, Trento, Italy Location and spatial extent support by Markus Neteler and Paul Kelly Various improvements by Markus Metz Multiple geometry columns support by Martin Landa, OSGeoREL, Czech
Technical University in Prague, Czech Republic

---

## Resources

- [Official v.in.ogr manual](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
