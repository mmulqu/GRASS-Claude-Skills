# v.external.out

**Category**: vector

## Description

Defines vector output format.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_external_out(output=None,format="ESRI_Shapefile",options=None,loadsettings=None,savesettings=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

---

---

## Detailed Description

v.external.out instructs GRASS to write vector maps in external data
format (e.g. ESRI Shapefile, Mapinfo, and others) using OGR
library . PostGIS data can be also written by
built-in GRASS-PostGIS data
provider .

---

## See Also

Related tools:
- [`v.external`](https://grass.osgeo.org/grass-devel/manuals/v.external.html)
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)
- [`v.out.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.out.ogr.html)
- [`v.out.postgis`](https://grass.osgeo.org/grass-devel/manuals/v.out.postgis.html)

---

## Resources

- [Official v.external.out manual](https://grass.osgeo.org/grass-devel/manuals/v.external.out.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.external.out.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
