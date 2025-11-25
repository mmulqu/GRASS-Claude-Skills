# v.external

**Category**: vector

## Description

Creates a new pseudo-vector map as a link to an OGR-supported layer or a PostGIS feature table.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_external(input,layer=None,where=None,output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

---

---

## Detailed Description

v.external creates new vector map as a link to external OGR layer or
PostGIS feature table. OGR (Simple Features Library) is part of the GDAL library, so you need to install GDAL to use v.external for external OGR layers. Note that a PostGIS feature table
can be linked also using built-in GRASS-PostGIS data driver (requires
GRASS to be built with PostgreSQL support).

---

## See Also

Related tools:
- [`v.external.out`](https://grass.osgeo.org/grass-devel/manuals/v.external.out.html)
- [`v.clean`](https://grass.osgeo.org/grass-devel/manuals/v.clean.html)
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [`v.import`](https://grass.osgeo.org/grass-devel/manuals/v.import.html)
- [`v.in.db`](https://grass.osgeo.org/grass-devel/manuals/v.in.db.html)
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)
- [`v.out.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.out.ogr.html)

---

## Authors

Radim Blazek, ITC-Irst, Trento, Italy PostGIS support by Martin Landa, GeoForAll (OSGeoREL) Lab, Czech
Technical University in Prague, Czech Republic

---

## Resources

- [Official v.external manual](https://grass.osgeo.org/grass-devel/manuals/v.external.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.external.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
